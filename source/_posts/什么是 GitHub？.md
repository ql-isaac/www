---
title: 什么是 GitHub？
urlname: ri2cx9
author: ql-isaac
date: "2021-08-14 16:52:10"
updated: "2023-06-13 23:27:05"
trans: What_is_GitHub
cover: "https://img.imql.life/GitHub.png"
categories:
  - Git 和 GitHub 从入门到实践
---

"hub"，乃中心之意，当你看了我的另外一篇[《什么是 Git》](https://www.ql-isaac.cn/2020/01/24/What_is_Git/)，对 Git 已经熟悉一些的时候，就会自然明白"GitHub"的含义。

<!-- more -->

## git commit 规范化

### 命令格式

```bash
git commit -m "<emoji代码> <type>(<scope>): <subject>"
```

### emoji 代码

[这里有一套约定俗成的 emoji 使用规范](https://gitmoji.dev/)，常用的如下表：

| emoji                 | emoji 代码                    | commit 说明                  |
| --------------------- | ----------------------------- | ---------------------------- |
| 🎨 (调色板)           | `:art:`                       | 改进代码结构/代码格式        |
| ⚡️ (闪电) /🐎 (赛马) | `:zap:`/`:racehorse:`         | 提升性能                     |
| 🔥 (火焰)             | `:fire:`                      | 移除代码或文件               |
| 🐛 (bug)              | `:bug:`                       | 修复 bug                     |
| 🚑 (急救车)           | `:ambulance:`                 | 重要补丁                     |
| ✨ (火花)             | `:sparkles:`                  | 引入新功能                   |
| 📝 (备忘录)           | `:memo:`                      | 撰写文档                     |
| 🚀 (火箭)             | `:rocket:`                    | 部署功能                     |
| 💄 (口红)             | `:lipstick:`                  | 更新 UI 和样式文件           |
| 🎉 (庆祝)             | `:tada:`                      | 初次提交                     |
| ✅ (白色复选框)       | `:white_check_mark:`          | 更新测试                     |
| 🔒 (锁)               | `:lock:`                      | 修复安全问题                 |
| 🍎 (苹果)             | `:apple:`                     | 修复 macOS 下的问题          |
| 🐧 (企鹅)             | `:penguin:`                   | 修复 Linux 下的问题          |
| 🏁 (旗帜)             | `:checkered_flag:`            | 修复 Windows 下的问题        |
| 🤖（机器人）          | `:robot:`                     | 修复 Android 下的问题        |
| 🍏 (绿苹果)           | `:green_apple:`               | 修复 iOS 下的问题            |
| 🔖 (书签)             | `:bookmark:`                  | 发行/版本标签                |
| 🚨 (警车灯)           | `:rotating_light:`            | 移除 linter 警告             |
| 🚧 (施工)             | `:construction:`              | 工作进行中                   |
| 👷 (工人)             | `:construction_worker:`       | 添加 CI 构建系统             |
| 💚 (绿心)             | `:green_heart:`               | 修复 CI 构建问题             |
| ⬆️ (上升箭头)         | `:arrow_up:`                  | 升级依赖                     |
| ⬇️ (下降箭头)         | `:arrow_down:`                | 降级依赖                     |
| 📌 (图钉)             | `:pushpin:`                   | 将依赖项固定到特定版本       |
| 📈 (上升趋势图)       | `:chart_with_upwards_trend:`  | 添加分析或跟踪代码           |
| ♻️ （回收）           | `:recycle:`                   | 重构代码                     |
| 🐳 (鲸鱼)             | `:whale:`                     | Docker 相关工作              |
| 🌐 (带子午线的地球仪) | `:globe_with_meridians:`      | 国际化与本地化               |
| ➕ (加号)             | `:heavy_plus_sign:`           | 增加一个依赖                 |
| ➖ (减号)             | `:heavy_minus_sign:`          | 减少一个依赖                 |
| 🔧 (扳手)             | `:wrench:`                    | 修改配置文件                 |
| 🔨 (锤子)             | `:hammer:`                    | 重大重构                     |
| ✏️ (铅笔)             | `:pencil2:`                   | 修复 typo                    |
| 💩 (粑粑…)            | `:poop:`                      | 写了辣鸡代码需要优化         |
| ⏪ (倒带)             | `:rewind:`                    | 恢复更改                     |
| 🔀 (交叉向右的箭头)   | `:twisted_rightwards_arrows:` | 合并分支                     |
| 📦 (包裹)             | `:package:`                   | 更新编译的文件或包           |
| 👽 (外星人)           | `:alien:`                     | 由于外部 API 更改而更新代码  |
| 🚚 (货车)             | `:truck:`                     | 移动或者重命名文件           |
| 📄 (正面朝上的页面)   | `:page_facing_up:`            | 增加或更新许可证书           |
| 💥 (爆炸)             | `:boom:`                      | 引入突破性的变化             |
| 🍱 (铅笔)             | `:bento:`                     | 增加或更新资源               |
| 👌 (OK 手势)          | `:ok_hand:`                   | 由于代码审查更改而更新代码   |
| ♿️ (轮椅)            | `:wheelchair:`                | 改善无障碍交互               |
| 💡 (灯泡)             | `:bulb:`                      | 给代码添加注释               |
| 🍻 (啤酒)             | `:beers:`                     | 醉醺醺地写代码…              |
| 💬 (消息气泡)         | `:speech_balloon:`            | 更新文本文档                 |
| 🗃 (卡片文件盒)        | `:card_file_box:`             | 执行与数据库相关的更改       |
| 🔊 (音量大)           | `:loud_sound:`                | 增加日志                     |
| 🔇 (静音)             | `:mute:`                      | 移除日志                     |
| 👥 (轮廓中的半身像)   | `:busts_in_silhouette:`       | 增加贡献者                   |
| 🚸 (孩童通行)         | `:children_crossing:`         | 优化用户体验、可用性         |
| 🏗 (建筑建造)          | `:building_construction:`     | 结构变动                     |
| 📱 (iPhone)           | `:iphone:`                    | 做响应式设计                 |
| 🤡 (小丑脸)           | `:clown_face:`                | 嘲弄事物（直译，这个没明白） |
| 🥚 (鸡蛋)             | `:egg:`                       | 增加彩蛋                     |
| 🙈 (看不见邪恶)       | `:see_no_evil:`               | 增加或更改 gitignore         |
| 📸 (照相机闪光灯)     | `:camera_flash:`              | 增加或更新截图               |
| ⚗️ (蒸馏器)           | `:alembic:`                   | 尝试新东西                   |
| 🔍 (放大镜)           | `:mag:`                       | SEO 优化                     |
| ☸️ (船的方向盘)       | `:wheel_of_dharma:`           | 关于 Kubernetes 的工作       |
| 🏷 (标签)              | `:label:`                     | 增加类型（FLow、Typescript） |

### type

用于说明 commit 的类别，有下表所示的可选项：

| 类别       | 含义                                                                                                                                                                                                       |
| ---------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `feat`     | 新功能（feature）                                                                                                                                                                                          |
| `fix/to`   | 修复 bug，可以是 QA 发现的 BUG，也可以是研发自己发现的 BUG。`fix`：产生 diff 并自动修复此问题，适用于一次提交直接修复问题。 `to`：只产生 diff 不自动修复此问题，适用于多次提交，最终修复问题提交时使用 fix |
| `docs`     | 文档（documentation）                                                                                                                                                                                      |
| `style`    | 格式（不影响代码运行的变动）                                                                                                                                                                               |
| `refactor` | 重构（即不是新增功能，也不是修改 bug 的代码变动）                                                                                                                                                          |
| `perf`     | 优化相关，比如提升性能、体验                                                                                                                                                                               |
| `test`     | 增加测试                                                                                                                                                                                                   |
| `chore`    | 构建过程或辅助工具的变动                                                                                                                                                                                   |
| `revert`   | 回滚到上一个版本                                                                                                                                                                                           |
| `merge`    | 代码合并                                                                                                                                                                                                   |
| `sync`     | 同步主线或分支的 Bug                                                                                                                                                                                       |

### scope

用于说明 commit 影响的范围，比如数据层、控制层、视图层等等，scope 可以省略。如果 commit 影响了不止一个 scope，可以使用`*`。

### subject

这个就是 commit 的说明了，不超过 50 个字符，结尾不加标点符号。

### 示例

某次提交：

```bash
git commit -m ":art: style: 格式修改"
```

GitHub 上的效果图：
![提交示例](https://img.imql.life/illustrations/FtXqxH5Zrw52sjQZYeL4YPoPxSia.png "提交示例")

## Fork

GitHub 是一个宝库，每当发现一个有趣的仓库，我们不仅仅会去点一个 Star（收藏）或 Watch（关注），我们还会去 Fork 一下该开源仓库：
![Fork](https://img.imql.life/illustrations/Fr_lzksrxr26IS1bshj5pYFserFE.png "Fork")
这样，该仓库会被克隆一份成为自己的仓库：
![自己的仓库](https://img.imql.life/illustrations/FuJF2bK2lg23BKTpG238UF7vEhmE.png "自己的仓库")
之后原仓库是不断有作者在更新，自己的仓库也想获得这些更新怎么办？其实很简单，如下图，这里正是在提示你原仓库的 main 分支已经超前了 13 次提交。
![upstream](https://img.imql.life/illustrations/FhY79nz_49aN-yMhAa0HjiWbs3nY.png "upstream")
我们只需要点击右侧的 Fetch upstream 从原仓库进行拉取，这样自己这边的仓库也是最新的了：
![fetch](https://img.imql.life/illustrations/FtBUjAI96oyE-IEjJl3ezasTP6Fv.png "fetch")
