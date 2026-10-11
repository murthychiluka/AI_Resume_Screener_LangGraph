# LangGraph Based Resume Screener
An LLM Chatbot based on LangGraph and LangChain that dynamically retrieves and processes resumes using RAG to perform resume screening.

# Introduction to the Project
## Project Overview:
This project endeavors to showcase a Proof of Concept (POC) of a Language Model (LLM) chatbot designed to revolutionize the resume screening process for hiring managers. Traditional methods rely heavily on keyword-based screening, often overlooking nuanced candidate qualifications and potential. In contrast, the proposed chatbot harnesses advanced LLM capabilities to handle unstructured, natural language data found in job descriptions and resumes, performing tasks akin to human recruiters but with greater efficiency and accuracy.

## Need for Innovation:
Despite the surge in job applications annually, current screening tools remain limited in their ability to effectively process and evaluate candidates' qualifications. Keyword-centric approaches struggle with the intricacies of human-written documents, leading to suboptimal candidate matches and prolonged hiring cycles. This underscores a critical need for integrating LLM-based technologies into the recruitment process to enhance precision and streamline operations.

# Role of RAG Frameworks
## Enhancing Chatbot Reliability:
RAG (Retriever-Augmented Generation) frameworks emerge as pivotal enhancements for chatbot reliability. By integrating external knowledge bases with LLM agents, RAG equips chatbots to contextualize user queries comprehensively. This augmentation significantly bolsters the accuracy and relevance of responses, particularly in data-intensive fields like recruitment where precise information retrieval is paramount.

## Addressing Complexity in Human Communication:
LLM Agents with RAG capabilities excel in deciphering intricate and ambiguous human prompts commonly found in job descriptions and resumes. While LLM generators adeptly handle such complexities, retrievers may struggle with multifaceted queries, impacting the quality of resume matches. Leveraging RAG frameworks can mitigate this challenge by improving the precision of resume retrieval, thereby optimizing candidate screening outcomes.


**Solution Over view:**
![Screenshot_125](https://github.com/Ajithbalakrishnan/LangGraph_Based_Resume_Screener/blob/main/assets/Solution_Overview.jpg)

**User Interface:**
![Screenshot_125](https://github.com/Ajithbalakrishnan/LangGraph_Based_Resume_Screener/blob/main/assets/UI.jpg)


**Based on:** 
- `streamlit`: Streamlit turns data scripts into shareable web apps in minutes.
All in pure Python. No front‑end experience required.
- `FaISS` : FAISS (Facebook AI Similarity Search) is an open-source library that helps developers quickly search for similar multimedia documents, such as images, videos, and text, within large datasets. It can also be used to cluster dense vectors. FAISS can be used to build indexes and perform searches with high speed and memory efficiency. 
- `Langchain` : LangChain is a framework designed to simplify the creation of applications using large language models. As a language model integration framework, LangChain's use-cases largely overlap with those of language models in general, including document analysis and summarization, chatbots, and code analysis.
- `hugginface`: For Embedding models   

- `Openai` `Gemnai` `HF Space` `Ollama`- LLM api integration
- ` LangGraph` - LLM agent integration (Yet to be implemented)


## How to Use Me?
Install MiniConda:
```
https://docs.anaconda.com/miniconda/miniconda-install/
```
Setup Conda environment
```
conda env create -f environment.yml
conda activate <env name>
```
Run the solution 
```
streamlit run src\main.py
```
***********************************************************************************************************************************
## LLM alone without RAG—→ may give hallucinations

1. What is an LLM alone?
LLM (Large Language Model) is an AI model like ChatGPT that understands your question and generates an answer based on patterns learned during training.

Imagine you ask:

Question: What is our company's annual leave policy?

The LLM has not been given your company's leave policy. It may still generate an answer that sounds correct, even though it doesn't know your actual policy.

For example, it might say, "Employees receive 20 days of annual leave."

But your company might actually provide only 15 days!

This is called a hallucination — when AI generates incorrect or unsupported information as if it were true.

2. What is RAG, and how does it help?
RAG stands for Retrieval-Augmented Generation.

It allows an LLM to retrieve relevant information from external documents or a knowledge base before generating an answer.

Step 1: User asks a question

"How many annual leave days do employees get?"

Step 2: RAG retrieves information

Finds the relevant company HR policy document, which says 15 days.

Step 3: LLM generates an answer

"According to the company HR policy, employees receive 15 days of annual leave."

RAG gives the LLM relevant information to use when answering. This can reduce hallucinations, although it cannot eliminate them completely.

3. LLM alone vs. LLM + RAG
LLM alone

LLM + RAG

Answers using what it learned during training and the current conversation.

Retrieves relevant external information before answering.

May not know your latest or private information.

Can access updated or private information if the knowledge source is available and authorized.

May guess when information is missing.

Can give answers grounded in retrieved documents.

Example: guesses company leave policy.

Example: checks the actual HR policy.

4. How does this apply to AWS DevOps?
Suppose you build an AI assistant to help troubleshoot your AWS environment.

LLM alone: You ask, "Why is my EC2 instance not connecting?" The LLM gives general troubleshooting suggestions.

LLM + RAG: The assistant retrieves your company's AWS architecture documents, troubleshooting guides, and runbooks, then provides advice based on those materials.

For example, it might find a runbook explaining that your private EC2 instance requires access through a bastion host or AWS Systems Manager.

One important point: RAG does not automatically access live AWS resources. To inspect actual instance status, logs, or security groups, the assistant would also need suitable tools and permissions.

Remember this simple formula:

LLM = Thinks and generates an answer.

RAG = Finds relevant information for the LLM.

LLM + RAG = Generates an answer using retrieved information.

Think of an LLM as a student answering from memory, while RAG lets the student consult the relevant textbook before answering.
