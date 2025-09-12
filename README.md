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
    
    from langchain_ollama import ChatOllama 
    llm = ChatOllama(model = "llama3.2")

    Or

    from langchain_openai import ChatOpenAI 
    llm = ChatOpenAI(model = "gpt-4o", temperature = 0)

2. Prompts - can dynamically input userinputs. Eg: 

    from langchain_core.promts import PromptTemplate
    promt_template = PromtTemplate.from_template("Tell me a joke about {topic}")
    promt_template.invoke({"topic": "cats"})

3. Document Loader - for using various data sources. Eg: 

    from langchain_community.document_loaders import PyPDFLoader
    pdf_loader = PyPDFLoader("filename.pdf")
    pdf_docs = pdf_loader.load()



