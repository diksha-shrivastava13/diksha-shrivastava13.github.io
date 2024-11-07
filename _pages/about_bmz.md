### Federal Ministry, BMZ

`AI Engineer | Jun '24 - Sept '24`

*(In partnership with GovTech Campus, Deutschland and Digital Product School)*

`The Problem of Language Model Reasoning and Analysis`
The Digital Product School connects companies and organisations to cross-functional teams of five, to deliver a complete product. The partner for this contract was the German Federal Ministry, BMZ.
The problem space requires the team to identify user pain points, ideate solutions, rapid prototype, and improve according to user tests to ship the product.
Large Language Models (LLMs) have poor performance on reasoning tasks like ARC-AGI, with the performance of OpenAI’s o1 models recorded at a sad 13-21%.
My contract with BMZ, interestingly enough, required me to solve this very problem to an extent that the resulting product can be accepted by the most challenging users: Policy Officers of 60+ Countries, in charge of overseeing programs under country partnerships with Germany.
The goal was to develop a LLM-based Decision-Making Aid for Country Policies with Reasoning and Analysis Pipelines from a complex hierarchy of unstructured reports.

I worked as an AI Engineer in a team of 5, and my main responsibility was to rapidly prototype a set of AI features which might satisfy user needs.

**PROJECT 1**

`Accept Handover`

Identified the pain points experienced by the Country policy Officers while dealing with a sea of reports. The pain points included:
* A complex hierarchy of unstructured reports
* Inconsistencies in schema and structure.
* Difficulty in determining how different reports and entities are related to each other. How the KPIs at lower level of hierarchy contribute to higher levels.
* Difficulty in understanding reports and drawing conclusions because of a lack of system.

The initial product developed during the first three months had a very simple RAG implementation which was inefficient for complex use.
* Implemented an efficient RAG pipeline with multiple features which responds in a maximum of 15 seconds.
* Changed the implementation from TypeScript to Python, removed unnecessary API calls.
* Handled the AI part of the entire Migration to Azure.

**PROJECT 2**

`Product Engineering`

Through the course of the contract, I developed the following features into the LLM system:
* Search capability for the user in natural language on one document.
* Search capability over multiple documents at once for the changing values of the same entities. Extraction of the impact matrix from documents along with KPIs at Programs and Projects levels, their associated risks, causes, impact, activities and applications.
* Recommendations for political dialogues for the project implementation and for improvement of programs.
* Risk analysis for factors which might lead to delays and non-completion of programs.
* Detection of Anomalies in multiple reports belonging to the same umbrella.
* Similarity analysis of growth of projects with overlapping factors.
* Extraction of learning lessons and scope of improvements for the programs.
* Analysis of KPIs growth and effect from projects to programs levels throughout the years.
* Extraction of fixed data from reports under the same umbrella and reporting anomalies like the changes in budget and durations.

**PROJECT 3**

`Research Engineering`

Since my contract was about the reasoning and analysis capabilities of LLMs, I had the opportunity to explore the following methods for this:
* Long Context Reorder during inference time
* Multiple LLMs, OCR and inference methods for RAG
* GraphRAG for relationship tracking
* Agentic Approach to produce planning data for each of the the tasks on which SLMs can be trained Standardising the structure of the reports
* Custom Metadata Augmentation for vector database

Finally, a pipeline where each relevant chunk of the document for the query is parsed thrice, with custom metadata conditions on the vector database and agentic parsing on inference with iterative, chained-response incremental retrieval for prompts tuned very carefully for each of the tasks in “Task 3” worked.

*Note: The data is NDA-bound and private due to state secrets and the risk of terrorism affecting the ongoing program activities.*