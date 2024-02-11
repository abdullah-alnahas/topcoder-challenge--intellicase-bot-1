# Context

This repository contains my solution to a [Topcoder challenge](https://www.topcoder.com/challenges/473d2563-9378-460d-b898-c894f39df706?tab=details). The objective of the challenge is to perform RAG over data related to Topcoder.

## Solution Description

In my solution for the challenge, I've divided the task into three main notebooks, each targeting a specific part of the problem. Let me walk you through my approach:

- In the first notebook, **01 - Data Transformation.ipynb**, my goal was to turn various document types into clean, structured text. I tackled different file formats like PDFs, Word documents, and even audio files. Here, I used `Mixtral 8*7`, an advanced LLM, to refine the raw data. I wrote code to ensure that each piece of content was clear and informative on its own. The final step here was to save this refined content into a CSV file.

- Moving to the second notebook, **02 - Query Preprocessing.ipynb**, I focused on preparing user queries for efficient processing. My first task was to make each query stand-alone. I used `Mixtral 8*7` for this too. It's quite adept at understanding and rephrasing queries. Then, I optimized these queries for a semantic search engine, ColBert, ensuring they were precise and ready for the next phase.

- The third notebook, **03 - RAG.ipynb**, is where I brought everything together. Using the ColBert search engine, I retrieved the most relevant information from the data processed earlier. With this information at hand, I then used `Mixtral 8*7` again to generate comprehensive and accurate responses to each user query. This part was crucial as it combined the search results with intelligent response generation. The output was two sets of CSV files, each containing the final responses to the public and hidden test queries.

My solution hinges on the effective use of `Mixtral 8*7` for data processing and query refinement, and ColBert for precise information retrieval. This synergy was key to addressing the Topcoder challenge efficiently.
