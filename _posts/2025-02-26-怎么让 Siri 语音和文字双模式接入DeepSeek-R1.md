---
layout: post
title: iPhone怎么让Siri语音和文字双模式接入DeepSeek-R1(V3)?
date: 2025-02-26 02:23:00 -0800
categories: AI
tags: [DeepSeek, AI, iOS, 教程]
---

### iOS怎么让Siri接入DeepSeek？

随着人工智能技术的飞速发展，许多人希望将强大的AI模型集成到日常工具中，比如将DeepSeek接入iOS的Siri，让语音助手变得更智能。本文将详细讲解如何通过快捷指令（Shortcuts）和DeepSeek API实现这一目标。无需复杂编程，只需几个步骤，就能让Siri调用DeepSeek的强大能力，回答问题或完成任务。

### 为什么选择DeepSeek？

DeepSeek-R1是一款由我国团队开发的开源AI模型，以其高效、低成本和高性能著称。它基于DeepSeek-V3（超过6000亿参数）构建，在多项基准测试中表现优异，媲美国际顶尖模型，一时间风靡全球。将其接入Siri，可以让你的语音助手具备更强的推理能力和自然语言处理能力，远超原生Siri的功能。

### 前置条件

在开始之前，你需要准备以下内容：

1. **DeepSeek API密钥**  
   前往[DeepSeek官网](https://www.deepseek.com/)注册账号，获取API密钥。新用户通常会获得一定数量的免费tokens（例如500万个），足够日常使用。

2. **iOS设备**  
   确保你的iPhone或iPad运行iOS 15或更高版本，并且已安装“快捷指令”（Shortcuts）应用。这是苹果官方提供的自动化工具。

3. **基础网络知识**  
   你需要知道如何发送HTTP请求（别担心，我们会用现成的工具简化这一步）。

### 步骤详解

以下是将Siri接入DeepSeek的具体步骤：

#### 1. 创建快捷指令

1. 打开iOS设备上的“快捷指令”应用。
2. 点击右上角的“+”按钮，创建一个新的快捷指令。
3. 点击“添加操作”，搜索并选择“获取文本”动作。这将允许你输入语音或文字作为DeepSeek的输入。

#### 2. 配置API请求

DeepSeek提供与OpenAI兼容的API接口，我们可以通过“快捷指令”的“获取URL内容”动作调用它。

1. 在快捷指令中，添加“获取URL内容”动作。
2. 设置以下参数：
   - **URL**: `https://api.deepseek.com/v1/chat/completions`
   - **方法**: POST
   - **标头**:
     - `Authorization`: `Bearer 你的API密钥`（将“你的API密钥”替换为从DeepSeek获取的实际密钥）
     - `Content-Type`: `application/json`
   - **请求正文**: 使用JSON格式，输入以下内容：
     ```json
     {
       "model": "deepseek-v3",
       "messages": [
         {"role": "user", "content": "快捷指令中的文本"}
       ],
       "max_tokens": 500
     }
     ```
     注意：将`"快捷指令中的文本"`设置为前一步“获取文本”的输出变量。

#### 3. 处理DeepSeek的响应

API调用后，DeepSeek会返回JSON格式的响应，我们需要提取其中的回答。

1. 添加“获取字典中的值”动作。
2. 设置“键”为`choices[0].message.content`，这将提取DeepSeek的回答文本。
3. 添加“朗读文本”或“显示结果”动作，让Siri读出或显示DeepSeek的回答。

#### 4. 将快捷指令绑定到Siri

1. 点击快捷指令右上角的设置图标。
2. 选择“添加到Siri”，录制一个触发短语，例如“嘿Siri，问DeepSeek”。
3. 保存后，你可以通过语音激活这个快捷指令。

#### 5. 测试与优化

- 说“嘿Siri，问DeepSeek”，然后提出一个问题，比如“今天天气如何？”。
- Siri会通过快捷指令发送请求给DeepSeek，并返回回答。
- 如果响应时间较长，可以调整`max_tokens`参数，减少输出长度。

#### 示例

以下是一个完整的快捷指令逻辑示例：

1. 获取文本（输入问题）
2. 获取URL内容（调用DeepSeek API）
3. 获取字典中的值（提取回答）
4. 朗读文本（输出结果）

### 注意事项

1. **网络依赖**  
   此方法需要互联网连接，因为Siri通过API调用DeepSeek的云端服务。如果想离线使用，可以探索DeepSeek的开源模型，但这需要更高阶的自托管技术。

2. **安全性**  
   API密钥是敏感信息，不要分享你的快捷指令文件。建议在“快捷指令”中加密存储，或定期更换密钥。

3. **性能限制**  
   DeepSeek的免费tokens有限，重度使用可能需要付费。此外，服务器繁忙时可能出现延迟。

### 结语

通过以上步骤，你已经成功将DeepSeek接入Siri，让你的语音助手变得更聪明。无论是学习、娱乐还是工作，这都是一个简单而强大的AI集成方案~

如果觉得太麻烦，或者看不懂专业性的内容不知道如何操作，也可以在萌萌的闲鱼购买~ 支持一下小站的运营~ 萌萌会持续产出优质的内容

下面是链接：
【闲鱼】https://m.tb.cn/h.TGtJYAN?tk=bTP1e9b3oXz CZ193 「我在闲鱼发布了【拒绝不用心！Siri接入语音文字双模式 DeepSeek-R】」 点击链接直接打开
