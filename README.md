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

#### LangChain - Prompt Templates 

A wrapper class around prompts. 

#### LangChain - ChatModels 

To talk to LLM. 

Historically, it was string input to LLM and a string output. However, currently it has evolved into coversational. 

Importing a ChatModel. Eg: <br>
from langchain_openai import ChatOpenAI


#### LangChain - Chain/ LCEL 

LCEL - LangChain Expression Language 

Output of one step become input of the next. Usage example using the LCEL syntax: <br>

chain = summary_prompt_template | llm

where <br>
A chain is created by using pipe operator - this is the LCEL syntax<br>
llm is the ChatModel object (Eg: llm = ChatOpenAI(temperature=0, model= "gpt-5")) <br>
summary_prompt_template is prompt template object

The chain resulting from this is called a Runnable Object! 

#### LCEL - Runnable Object 

A runnable object can be invoked to get a response. 

#### Different ChatModels 

Any chatmodels can be used in langchain. Examples include: 

1. Proprietary models like chatGPT 
2. Opensource models using Ollama 

### AI Agents  

------------ Project Requirements -----------

UV: 
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

gitignore: 
Those information that I don't want to commit 

Ollama: 

- Download Ollama - https://ollama.com/download/windows
- Install it 
- ollama --help 
- ollama pull gemma3:270m
