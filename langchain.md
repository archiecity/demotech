```python
from langchain_openai import ChatOpenAI
# 负责连接模型
from langchain_huggingface import HuggingFaceEmbeddings
# 将数字转换成文字
from langchain_core.prompts import PromptTemplate
#提示词模板,用来设定角色，划定范围，整合资料塞给它
from langchain_core.output_parsers import StrOutputParser
#输出过滤器，过滤大模型返回的消息对象，token消耗量，停止原因，多层级字典结构
from langchain_core.output_parsers.json import JsonOutputParser
#结构化输出数据

```



## 模型连接基本信息

```python
qwen_llm = ChatOpenAI(
    #模型名称
    model="qwen3-32b", 
    #密钥
    api_key="sk-643ef4c9f4f",
    #模型地址
    base_url="https:///compatible-mode/v1",
    #控制模型回答的随机性，接近0是严谨，接近2是发散
    temperature=0.2,
    #控制专属模型的参数，比如说让enablethinking=False就是要求不要返回思考过程
    model_kwargs={"extra_body": {"enable_thinking": False}},
)

```

## 获取父目录 os 库的使用

```python
import os # Operating System 操作系统库，多用于高效管理文件

# 获取当前文件 (rag.py 或 normal_rag.py) 所在的绝对路径的父目录的父目录，即项目根目录 symbol/
BASE_DIR = os.path.dirname(os.path.dirname(os.path.dirname(os.path.abspath(__file__))))
# __file__ 表示相对路径
# os.path.abspath（）表示获取文件的绝对路径
# os.path.dirname（）获得父地址

# 将根目录与 vdb 文件夹拼接成相对的绝对路径
DB_PATH = os.path.join(BASE_DIR, "vdb")

# 建议用相对路径来处理
```

