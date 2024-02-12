# Context

This repository contains my solution to a [Topcoder challenge](https://www.topcoder.com/challenges/473d2563-9378-460d-b898-c894f39df706?tab=details). The objective of the challenge was to perform RAG over data related to Topcoder. My solution was among the [top 5](https://www.topcoder.com/challenges/473d2563-9378-460d-b898-c894f39df706?tab=submissions) solutions.

## Solution Description

In my solution for the challenge, I divided the task into three main notebooks, each targeting a specific part of the problem. Let me walk you through my approach:
 
- In the first notebook, **01 - Data Transformation.ipynb**, my goal was to convert various document types into clean text ready for indexing. I tackled different file formats like PDFs, PowerPoint .pptx, Word documents, and even audio files using Langchain. After extracting the raw text, I utilized an LLM, `Mixtral 8*7`, to post-process and refine the quality of the extracted raw data. I also kept the original extracted content to have a reference point in case the LLM hallucinated content while refining it. The final step here was to save this refined content into a CSV file.

- Moving to the second notebook, **02 - Query Preprocessing.ipynb**, I focused on preparing user queries for efficient processing. My first task was to make each query stand-alone. I used an LLM, `Mixtral 8*7`, for this too. This is important because some queries reference previous queries. Then, I optimized these queries for a semantic search engine, also by prompting an LLM to remove query-irrelevant words from the questions, ensuring they were precise and ready for the next phase.

- The third notebook, **03 - RAG.ipynb**, is where I brought everything together. Using ColBERT, I indexed both the raw and the refined data from the first step. Then, I moved on to generating answers for user questions. To do this, first, I retrieved relevant information from ColBERT. With this information at hand, I then used `Mixtral 8*7` to generate comprehensive and accurate responses to each user query. This part was crucial as it combined the search results with intelligent response generation. The output was two sets of CSV files, each containing the final responses to the public and hidden test queries.

My solution hinges on the effective use of `Mixtral 8*7` for data processing, query refinement and answer generation, and ColBERT for precise information retrieval. This synergy was key to addressing the Topcoder challenge efficiently.

## Key Technologies

- Langchain, unstructured, llama index
- Mixtral 8*7 accessed through the Anyscale API
- ColBERT
