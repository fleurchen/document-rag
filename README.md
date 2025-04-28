# document-rag
基于文档资料的智能问答系统-简易版

# 问答系统搭建流程
## 文档嵌入到向量数据库
### 1 使用PDFPlumberLoader加载文档列表
### 2 使用文档切割RecursiveCharacterTextSplitter设置chunk的大小和重叠部分大小，将文档列表切割
### 3 使用Chroma和OllamaEmbeddings将切割后的文档形成向量数据库持久化到磁盘位置
## 问答知识链
### 1 加载持久化向量数据库到vector_store
### 2 基于向量数据存储创建检索器retriver
### 3 创建问答子链 create_stuff_documents_chain
### 4 创建历史记录搜索子链 create_history_aware_retriever
### 5 创建代理链（联合3，4两个链）
### 6 创建session记录数组，将不同的历史记录归于不同的session
### 7 创建最终链RunnableWithMessageHistory
## 创建api
### 1 创建FASTAPI
### 2 设置路由地址及调用链
### 3 启动uvicorn，设置端口
## 使用streamlit搭建简易的前端页面
### 1 RemoteRunnable调用远程api并传递前端输入的问题
### 2 使用streamlit run page.python启动页面

