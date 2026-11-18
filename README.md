# Job-Search Agent

A semantic job search system with a tool-calling agent, built to explore how retrieval, ranking, and LLM agents work together on a changing jobs index.

**Status: in progress.** The design below is planned and not yet implemented.

## Problem
Keyword search misses relevant jobs when the wording differs. This project searches jobs by meaning and lets a user find roles through conversation.

## Planned architecture
1. **Data:** a public jobs dataset, cleaned and stored in a database
2. **Embeddings:** Sentence Transformers for job descriptions
3. **Retrieval:** vector search with filters (location, skills)
4. **Ranking:** a re-ranking step on top of the first retrieval results
5. **Agent:** LangChain agent with tools (`search_jobs`, `filter_by_skill`, `get_job_details`) and structured outputs
6. **API:** FastAPI backend
7. **Deployment:** Docker, then a cloud deploy

## Evaluation plan
- A set of 20-30 test queries with the jobs I'd expect for each
- Measure hit rate with and without the re-ranker
- Note failure cases, such as queries that return nothing relevant

## Tech
Python, FastAPI, LangChain, Sentence Transformers, ChromaDB or pgvector, SQL, Docker

## Build log
- [18/112026]: Repo created, architecture planned
