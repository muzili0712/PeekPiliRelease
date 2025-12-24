> ⚠️ **重要说明**  
> 
> 本人是小白开发者，本项目基于个人兴趣开发，仅供学习交流使用。  
> 
> **应用肯定有 bug，不喜勿喷** 😅
> 
> **免责声明**：
> - 本项目仅用于学习和研究目的，不提供任何商业服务
> - 使用本软件产生的任何后果由使用者自行承担
> - 请遵守相关法律法规，不得用于非法用途
> - 如有问题或建议，欢迎友好交流，不喜勿喷
> 
> 感谢理解与支持 🙏

<br/>

<div align="center">
    <img width="200" height="200" src="assets/images/logo/logo.png">
</div>



<div align="center">
    <h1>PeekPili</h1>
    <p>基于 PiliPlus 二次开发，集成 TVbox 视频源播放功能</p>
    
<img src="assets/screenshots/510shots_so.png" width="32%" alt="home" />
<img src="assets/screenshots/174shots_so.png" width="32%" alt="home" />
<img src="assets/screenshots/850shots_so.png" width="32%" alt="home" />
<br/>
<img src="assets/screenshots/main_screen.png" width="96%" alt="home" />
<br/>
</div>


<br/>

## 项目简介

**PeekPili** 是基于 [PiliPlus](https://github.com/bggRGjQaUbCoE/PiliPlus) 进行二次开发的应用，在保留原版 PiliPlus 全部功能的基础上，新增了 **TVbox 视频源播放功能**，支持多种视频源格式，让您可以在一个应用中享受丰富的第三方视频源内容。

> 📌 **关于 PiliPlus 原版功能**  
> 本项目完整保留了 PiliPlus 的所有功能，如需了解原版的详细功能特性，请访问原版 GitHub 仓库：  
> **[👉 PiliPlus 原版仓库](https://github.com/bggRGjQaUbCoE/PiliPlus)**

**✨ 多平台支持** - PeekPili 支持 Android、iOS、Pad、Windows 等平台，无论您使用什么设备，都能享受一致的使用体验。

## 适配平台

- [x] **Android** - 手机、平板完美支持
- [x] **iOS** - iPhone、iPad 原生体验
- [x] **Pad** - 平板设备优化适配
- [x] **Windows** - 桌面端完整功能
<br/>

## 技术栈

- **Flutter** - 基于 Flutter 框架开发
- **播放器** - MPV 和 MDK

<br/>

## 核心功能

### 📺 TVbox 视频源功能（新增）

本项目在 PiliPlus 基础上新增了完整的 TVbox 视频源播放功能，支持多种视频源格式。

#### 支持的视频源类型

本项目全平台支持以下三种类型的视频源：

1. **T4 源（TVbox Type4）**
   - 支持标准 T4 API 接口源
   - 支持 HTTP API 格式的视频源
   - 完整的视频分类、搜索、详情、播放功能
   - 支持多站源切换和管理
   - 支持解析接口配置

2. **T3 源 - CatJS 源（猫源）**
   - 支持 cat 格式的 JavaScript 爬虫源
   - 支持 ES Module 格式的 JS 源
   - 支持 **Open 版本**和 **NodeJS 版本**两种猫源格式
   - 内置常用工具库（CryptoJS、lodash、cheerio 等）
   - 支持远程 URL 和本地代码两种方式

3. **T3 源 - Python 源（py 源）**
   - 支持 Python 爬虫脚本源
   - 完整的爬虫接口支持

#### 源助手功能

为了方便用户测试和调试视频源，项目内置了强大的**源助手**工具：

- **CatJS 源调试助手**
  - 支持测试 cat 格式的 JS 爬虫源
  - 支持远程 URL 和代码输入两种模式
  - 可测试所有爬虫方法：
    - `homeContent` - 首页分类
    - `homeVideoContent` - 首页推荐视频
    - `categoryContent` - 分类内容
    - `searchContent` - 搜索内容
    - `detailContent` - 详情内容
    - `playerContent` - 播放内容
  - 实时查看测试结果，支持 JSON 格式化显示
  - 支持清除缓存，方便重新测试

- **Python 源测试助手**
  - 支持测试 Python 爬虫源
  - 支持 URL 和代码两种输入方式
  - 完整的错误提示和调试信息

#### TVbox 功能特性

- **多源管理**
  - 支持配置多个视频源接口
  - 支持本地和远程配置文件
  - 快速切换不同视频源

- **视频浏览**
  - 首页推荐内容
  - 分类浏览（电影、电视剧、综艺等）
  - 高级筛选功能（年份、类型、排序等）
  - 搜索功能

- **播放功能**
  - 多线路播放源选择
  - 画质选择
  - 解析接口支持
  - 弹幕搜索和加载
    - 内置弹幕搜索功能，快速查找精彩弹幕
    - 支持动态弹幕效果
    - 支持渐变色弹幕显示

- **个人功能**
  - 收藏管理
  - 观看历史
  - 我的页面

<br/>

## 功能列表

### TVbox 功能

- [x] T4 源支持（TVbox Type4）
  - [x] HTTP API 源
  - [x] 多站源管理
  - [x] 解析接口配置

- [x] T3 源支持
  - [x] CatJS 源（猫源）
    - [x] cat 格式支持
    - [x] ES Module 格式支持
    - [x] Open 版本支持
    - [x] NodeJS 版本支持
    - [x] 内置工具库
  - [x] Python 源（py 源）
    - [x] Python 爬虫脚本执行
    - [x] 完整爬虫接口支持

- [x] 源助手
  - [x] CatJS 源调试助手
  - [x] Python 源测试助手
  - [x] 实时测试和调试
  - [x] 结果查看和复制

- [x] 视频浏览
  - [x] 首页推荐
  - [x] 分类浏览
  - [x] 高级筛选
  - [x] 搜索功能

- [x] 播放功能
  - [x] 多线路播放
  - [x] 画质选择
  - [x] 解析接口
  - [x] 弹幕支持
    - [x] 内置弹幕搜索功能
    - [x] 支持动态弹幕
    - [x] 支持渐变色弹幕

- [x] 个人功能
  - [x] 收藏管理
  - [x] 观看历史

> 💡 **查看完整功能列表**  
> 如需了解 PiliPlus 原版的所有功能特性，请访问原版 GitHub 仓库：  
> **[👉 PiliPlus 原版仓库](https://github.com/bggRGjQaUbCoE/PiliPlus)**

<br/>

## 下载

可以通过右侧 release 进行下载或拉取代码到本地进行编译

<br/>

## 使用说明

### TVbox 功能使用

1. **配置视频源**
   - 进入设置页面，找到 TVbox 相关设置
   - 配置视频源接口地址（支持本地和远程配置）
   - 选择要使用的视频源

2. **使用源助手**
   - 进入源助手页面
   - 选择要测试的源类型（CatJS 或 Python）
   - 输入源地址或代码
   - 选择测试方法并填写参数
   - 查看测试结果

3. **浏览和播放**
   - 在 TVbox 模式下浏览视频内容
   - 支持分类筛选和搜索
   - 选择播放线路和画质
   - 享受流畅的播放体验

> 📖 **原版功能使用说明**  
> 关于 PiliPlus 原版功能的使用方式，请参考原版 GitHub 仓库的使用文档：  
> **[👉 PiliPlus 原版仓库](https://github.com/bggRGjQaUbCoE/PiliPlus)**

<br/>

## 常见问题

### Q: 有没有 TV 端？

**A:** 没有。本项目目前不支持 TV 端。

> 💡 **推荐**  
> 如果您仅仅是安卓手机和 TV 用户，强烈推荐使用 **ok影视**，因为兼容性最强、覆盖性最广。

### Q: 支不支持 jar 包？

**A:** 不支持。

### Q: 播放是否支持本地代理（如 127.0.0.1:9978 格式）？

**A:** 不支持。播放不支持本地代理格式。

<br/>

## 声明

此项目基于 [PiliPlus](https://github.com/bggRGjQaUbCoE/PiliPlus) 进行二次开发，仅用于学习和测试，请于下载后24小时内删除。

在此致敬原作者：
- [guozhigq/pilipala](https://github.com/guozhigq/pilipala)
- [orz12/PiliPalaX](https://github.com/orz12/PiliPalaX)
- [bggRGjQaUbCoE/PiliPlus](https://github.com/bggRGjQaUbCoE/PiliPlus)

感谢使用

<br/>

## 致谢

- [PiliPlus](https://github.com/bggRGjQaUbCoE/PiliPlus) - 原版项目
- [flutter_meedu_videoplayer](https://github.com/zezo357/flutter_meedu_videoplayer)
- [media-kit](https://github.com/media-kit/media-kit)
- [dio](https://pub.dev/packages/dio)
- 等等

<br/>
<br/>
<br/>

## Star History

<a href="https://www.star-history.com/#bggRGjQaUbCoE/PiliPlus&Date">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=bggRGjQaUbCoE/PiliPlus&type=Date&theme=dark" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=bggRGjQaUbCoE/PiliPlus&type=Date" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=bggRGjQaUbCoE/PiliPlus&type=Date" />
 </picture>
</a>

