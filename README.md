# Xrona
-
一个简单的Windows桌面AI助手，可联网搜索，语音识别命令，图片识别及生成

具体实现（由Deepseek-R1生成）
-
技术栈概述
-
前端：C# + WinUI 3（桌面应用）
LLM 引擎：Llama.cpp（本地部署）
API 调用：Python（作为中间层，处理逻辑和集成）
语音识别：Whisper（本地部署）

为什么这个方案很棒？
-
本地化与隐私：所有核心功能（LLM、语音识别）都本地运行，用户数据完全可控，特别适合注重隐私的场景。

性能与效率：C#和WinUI 3的组合在Windows平台上性能出色，Llama.cpp和Whisper的本地部署也能充分利用硬件资源。

灵活性：Python作为中间层，可以灵活处理复杂的逻辑和集成，同时方便调用Llama.cpp和Whisper的API。

具体实现思路
-
前端：C# + WinUI 3
-

功能实现：

主界面：一个简洁的输入框和对话历史展示区域。

语音按钮：点击后调用Whisper进行语音识别。

设置页面：配置Llama.cpp模型路径、Whisper参数等。

优势：

原生支持Windows，性能优秀。

可以直接调用本地API，与Python中间层无缝对接。

LLM 引擎：Llama.cpp
-

实现方式：

将Llama.cpp编译为可执行文件，通过Python调用其API。

在Python中处理输入输出，将结果返回给C#前端。

优势：

完全本地运行，无需联网。

支持自定义模型，灵活性高。

API 调用：Python
Python 中间层：负责连接前端、Llama.cpp和Whisper。
-
功能实现：
接收前端的文本或语音输入。
调用Llama.cpp生成回复。
调用Whisper进行语音识别。
将结果返回给前端。


语音识别：Whisper
-
实现方式：

将Whisper模型部署在本地，通过Python调用。
将语音输入转换为文本，发送给Llama.cpp生成回复。

优势：

本地运行，隐私有保障。
识别准确率高，支持多语言。

About Future：
-
此项目将在几个月内达到基本可用水平，届时将会发布alpha版本
如果你参与开发，提交你的想法到issues并且上传文件
