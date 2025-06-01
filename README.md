# DocRead_AI
### Project Overview:
This project aims to develop a robust Retrieval-Augmented Generation (RAG) system designed to efficiently extract and provide accurate answers from life insurance policy documents. By leveraging advanced retrieval and generative AI techniques, the system will enable users to query a policy document and receive precise, context-aware responses, reducing the need for manual searches and improving accessibility.

### Objective: 
The goal of the project will be to build a robust generative search system capable of effectively and accurately answering questions from a policy document. We will be using a single long life insurance policy document for this project.

### Dataset:
Insurance Policy Dataset 

### Design: 
#### Embedding Layer
•	Data Loading: Utilized LangChain's PyPDFLoader to extract pages from the document.
•	Preprocessing: Removed pages with minimal information to improve retrieval quality.
•	Chunking Strategy: Tested various methods and selected RecursiveCharacterTextSplitter for its semantic chunking capabilities.
#### Search Layer
We designed key queries to target important sections of the document:
1.	Eligibility: What is the eligibility for Member Life Insurance?
2.	Claim Limits: What is the maximum claim amount for Member Accidental Death and Dismemberment Insurance?
3.	Premium Payment: What happens if a policy member fails to pay the premium?
For retrieval, we opted for Sentence Transformers over Chromadb as they demonstrated higher efficiency in identifying contextual relevance.
Re-Ranking Strategy
•	Implemented AutoModelForSequenceClassification for re-ranking retrieved results.
•	Used the pre-trained GPT-3.5 Turbo model to refine response selection.
#### Generation Layer
We structured our final prompt with few-shot examples and clear instructions:
-	Analyze retrieved chunks thoroughly before generating a response.
-	Prioritize results with the highest predicted score.
-	Resolve contradictions by reasoning through differences.
-	Ensure responses are concise yet detailed.
-	Use headings for clarity when necessary.
-	Acknowledge missing information when relevant.
-	Maintain a professional and informative tone.
#### Bot Implementation
We developed a bot that:
-	Accepts user queries related to insurance policies.
-	Retrieves relevant information using the optimized search pipeline.
-	Generates responses following structured reasoning.

### Technology User: 
- OpenAI GPT-3.5-Turbo
- Langchain
- ChromaDB
- Huggingface Sentence Transformer


  
