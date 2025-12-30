# JS源文件编写说明

## 重要提示

本壳子使用 flutter_js，cheerio 的 `.text()` 方法会返回空字符串，且补丁没有生效。

**必须使用 `getText()` 函数替代 `.text()` 方法。**

---

## getText() 函数

在每个源文件开头添加这个函数：

```javascript
function getText($elem) {
    if (!$elem || $elem.length === 0) return '';
    let text = '';
    try {
        text = $elem.text();
        if (text && text.trim()) return text.trim();
    } catch (e) {}
    try {
        const html = $elem.html();
        if (html) {
            text = html.replace(/<[^>]*>/g, '').replace(/&nbsp;/g, ' ').replace(/\s+/g, ' ').trim();
            if (text) return text;
        }
    } catch (e) {}
    return '';
}
```

---

## 使用方法

### ❌ 错误写法
```javascript
vod_name: $item.find('.title').text().trim()
```

### ✅ 正确写法
```javascript
vod_name: getText($item.find('.title'))
```

---

## 代码示例

### homeVod()
```javascript
async function homeVod() {
    const html = await request(`${HOST}/`);
    const $ = load(html);
    const videos = [];
    
    $('.item').each((index, item) => {
        const $item = $(item);
        videos.push({
            vod_id: $item.find('a').attr('href'),
            vod_name: getText($item.find('.title')),
            vod_pic: $item.find('img').attr('src'),
            vod_remarks: getText($item.find('.update'))
        });
    });
    
    return JSON.stringify({ list: videos });
}
```

### 多层备用方案（推荐）

对于标题等关键字段，建议使用多层备用：

```javascript
const $title = $item.find('.title');
const $link = $item.find('a');
const $img = $item.find('img');

let vodName = $title.attr('title') || '';
if (!vodName) vodName = $link.attr('title') || '';
if (!vodName) vodName = $img.attr('alt') || '';
if (!vodName) vodName = getText($title);
```

### category()
```javascript
async function category(tid, pg, filter, extend) {
    const html = await request(url);
    const $ = load(html);
    const videos = [];
    
    $('.video-item').each((index, item) => {
        const $item = $(item);
        videos.push({
            vod_id: $item.find('a').attr('href'),
            vod_name: getText($item.find('.title')),
            vod_pic: $item.find('img').attr('src'),
            vod_remarks: getText($item.find('.update'))
        });
    });
    
    return JSON.stringify({ list: videos });
}
```

### detail()
```javascript
async function detail(id) {
    const html = await request(id);
    const $ = load(html);
    
    const vod = {
        vod_id: id,
        vod_name: getText($('.title h1')),
        vod_pic: $('.poster img').attr('src'),
        vod_content: getText($('.description')),
        // ...
    };
    
    return JSON.stringify({ list: [vod] });
}
```

---

## 注意事项

1. **属性提取正常**：`attr()` 方法不受影响，可以正常使用
2. **map() 方法**：使用 `getText()` 替代 `.text()`
   ```javascript
   const types = $item.find('a').map((i, a) => getText($(a))).get();
   ```
3. **链式调用**：先获取元素，再用 `getText()`
   ```javascript
   const $title = $item.find('.title');
   const name = getText($title);
   ```

---

## 完整模板

```javascript
import { load, _ } from 'assets://js/lib/cat.js';

let HOST = 'https://example.com';

// 必须添加
function getText($elem) {
    if (!$elem || $elem.length === 0) return '';
    let text = '';
    try {
        text = $elem.text();
        if (text && text.trim()) return text.trim();
    } catch (e) {}
    try {
        const html = $elem.html();
        if (html) {
            text = html.replace(/<[^>]*>/g, '').replace(/&nbsp;/g, ' ').replace(/\s+/g, ' ').trim();
            if (text) return text;
        }
    } catch (e) {}
    return '';
}

async function request(reqUrl) {
    let res = await req(reqUrl, { method: 'GET' });
    return res.content;
}

function init(cfg) {
    HOST = cfg.ext || HOST;
}

async function home(filter) {
    return JSON.stringify({ class: [], filters: {} });
}

async function homeVod() {
    // 使用 getText() 替代 .text()
}

async function category(tid, pg, filter, extend) {
    // 使用 getText() 替代 .text()
}

async function search(wd, quick) {
    // 使用 getText() 替代 .text()
}

async function detail(id) {
    // 使用 getText() 替代 .text()
}

async function play(flag, id, flags) {
    // 播放地址解析
}

export function __jsEvalReturn() {
    return {
        init, detail, home, play, search, homeVod, category
    };
}
```

---

## 检查清单

- [ ] 已添加 `getText()` 函数
- [ ] 所有 `.text()` 已替换为 `getText()`
- [ ] 关键字段使用了多层备用方案
- [ ] 有错误处理（try-catch）
