```bash
cd easy-data-x-ai/code

# 安装依赖
python - m pip install --upgrade -r requirements.txt
pip install --upgrade -r requirements.txt

# 复制 .env.example 为 .env
cp .env.example .env

# 在 .env 文件中填写你的真实 API Key
vim .env

# 运行示例代码
python D1/d1_1_base.py
```
<img width="2766" height="1850" alt="image" src="https://github.com/user-attachments/assets/04e223f1-884d-4012-ae43-35e668a6a169" />

```bash
from langchain.chat_models import init_chat_model

llm = init_chat_model(
    "tencent/Hunyuan-MT-7B",
    model_provider="openai",  # 通过 OpenAI 兼容接口调用
    base_url="https://api.siliconflow.cn/v1",
    api_key="YOUR_API_KEY",
)

response = llm.invoke([
    ("system", "你是一个简洁高效的技术助手。用中文回答，尽量用一两句话。"),
    ("user", "什么是 RAG？"),
])

print(response.content)
```
<img width="2782" height="1886" alt="image" src="https://github.com/user-attachments/assets/92d9e611-8c60-473f-b888-6349531280a0" />

多轮对话
```bash
from langchain.chat_models import init_chat_model

llm = init_chat_model(
    "tencent/Hunyuan-MT-7B",
    model_provider="openai",
    base_url="https://api.siliconflow.cn/v1",
    api_key="YOUR_API_KEY",
)

messages = [
    ("system", "你是一个简洁高效的技术助手。"),
    ("user", "什么是 RAG？"),
    ("assistant", "RAG 是检索增强生成，先从知识库检索相关内容，再让模型基于这些内容生成回答。"),  # 让模型在回答你追问的下一个问题之前，知道你们之前聊了什么，知道下一个问题中的"它"是谁。
    ("user", "它和直接把文档塞进 Prompt 有什么区别？"),
]

response = llm.invoke(messages)

print(response.content)
```
<img width="2784" height="1882" alt="image" src="https://github.com/user-attachments/assets/5d2176c7-9187-4025-aad3-ce0ce3dd68d1" />

流式输出
```bash
from langchain.chat_models import init_chat_model

llm = init_chat_model(
    "tencent/Hunyuan-MT-7B",
    model_provider="openai",
    base_url="https://api.siliconflow.cn/v1",
    api_key="YOUR_API_KEY",
)

for chunk in llm.stream([
    ("system", "你是一个技术助手。"),
    ("user", "用三句话解释什么是向量数据库。"),
]):
    print(chunk.content, end="", flush=True)

print()  # 最后换行
```
<img width="2778" height="1876" alt="image" src="https://github.com/user-attachments/assets/0382fbc3-12a0-404e-bce8-64db8cbb5c7b" />

tool use
<img width="2578" height="1926" alt="image" src="https://github.com/user-attachments/assets/9484761a-37e2-46b8-ad6f-d26e6050ddae" />



