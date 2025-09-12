### DEVEOPING AI AGENT WITH LANGCHAIN & LANGGRAPH - A TUTORIAL 
- An elaborate coverage of AI Agent and RAG 
- LangChain Ecosystem: LangSmith and LangGraph 
- Prompt Engineering and Production 

#### LangChain

- A framework for developing application powered by LLMs 

Components of LangChain 
- Development using LangGraph - to build stateful agents with first-class streaming and human-in-the-loop support. 
- Productionalization using LangSmith - to inspect, monitor and evaluate the chain 
- Deployment - LangGraph cloud (not covered)

More details: https://www.langchain.com/

Essentially, developers not required to know how LLMs or ML works to develop an agent. 

LangChain Features: 
1. several llms available and can switch between llms. Examples: 
    
    from langchain_ollama import ChatOllama <br>
    llm = ChatOllama(model = "llama3.2")

    Or

    from langchain_openai import ChatOpenAI <br>
    llm = ChatOpenAI(model = "gpt-4o", temperature = 0)

2. Prompts - can dynamically input userinputs. Eg: 

    from langchain_core.promts import PromptTemplate<br>
    promt_template = PromtTemplate.from_template("Tell me a joke about {topic}")<br>
    promt_template.invoke({"topic": "cats"})

3. Document Loader - for using various data sources. Eg: 

    from langchain_community.document_loaders import PyPDFLoader <br>
    pdf_loader = PyPDFLoader("filename.pdf")<br>
    pdf_docs = pdf_loader.load()



------------ Project Requirements -----------

1. Bootrapping the project using uv 
2. pip install uv (if uv is not installed in the system)
3. uv init 
    - This will create venv named langchain_pjt (this is the name of the folder)
4. uv add langchain
    - This will install all the packages and dependecies of langchain
5. uv add langchain-openai
    - Every provider of LLM has their own packages, which are maintained by the provider itself. 
6. uv add python-dotenv
    - This helps add environment variables from .env file. To save api keys. 
7. uv add black isort 
    - For formatting the code
