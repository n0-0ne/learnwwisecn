# Wwise 基础知识 (12) 设计师和程序员之间的任务分工

目录

- 设计师和程序员之间的任务分工- 声音设计师的职责- 音频程序员的职责- 项目规划

## 设计师和程序员之间的任务分工也许您已经清楚，Wwise 采取不同于其他声音引擎的声音设计和集成方式。声音设计师被赋予了更大的控制权，这意味着过去通常由开发人员处理的、耗费时间的重复性工作现在已降到了最低水平，因此声音设计师和开发人员可以专门处理更加有趣的创造性工作。省去大量对接工作后，两组人员可以各显神通，更加高效地进行协作。Wwise 认识到声音设计师和音频程序员两者之间存在角色差异，因此为他们分派了特定的任务。
## 声音设计师的职责声音设计师负责：
- 创建音频层级结构和行为。- 创建音频 Event（事件）。- 将音频 Event 集成到世界编辑应用程序中。- 设置声音属性和源。- 定义 3D 声音定位。- 为所有声音确定音频信号连线和混音要素。- 指定实时参数控制和游戏状态。- 为游戏中的各种环境定义效果属性。- 定义音量、LPF 声障和声笼属性。- SoundBank（声音库） 管理和优化。- 为多个平台定制音频。- 平台语言本地化。

## 音频程序员的职责音频程序员负责：
- 将 Wwise 声音引擎集成到游戏引擎中。- 使用代码集成音频事件。- 注册游戏中发声的 Game Object。- 调用 `AK::SoundEngine::PostEvent()` 方法触发包含一个或多个音频动作的事件。- 使用 Soundbank Definition File（SoundBank定义文件）和 File Packager（文件打包工具） 管理由声音设计师或游戏指定的 Soundbank 的加载和卸载。- 根据Listener的坐标系统设定 3D Game Object的位置。- 触发状态和切换开关，并更新实时参数控制。- 设定应用于游戏声音的每个环境效果的百分比。- 计算每个Game Object相对于Listener的声障和声笼值。- 管理内存资源，包括加载和卸载 SoundBank、处理流、注册插件等。- 编写源和效果器插件。声音引擎的插件架构允许游戏开发人员扩展 Wwise 的功能来满足他们的特定游戏需求。- 将 SoundFrame 集成到开发工具中。

## 项目规划在项目初期，音频程序员和声音设计师应碰头讨论，将如何为游戏音频所分配各种资源。这些资源包括但不限于内存、磁盘空间、流数量和 SoundBank 大小。

根据游戏设计和技术限制，设计师和开发人员必须共同决定：
- 游戏引擎如何集成和触发 Event。- Project Hierarchy（工程层级结构）和 Workgroup（工作组）的 Work Unit（工作单元）组织。- 游戏玩家视角和 Listener定位。- Soundbank 加载/卸载策略。- 音乐集成与互动音乐的特别要求。- 哪些参数应该用作实时参数控制 （RTPC）。- 游戏的哪些全局元素可以驱动 Mix（混音）和 State（状态）机制。- 哪些声音结构需要 Switch（切换开关）机制。

