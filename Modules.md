# Serengeti Memory Agent — Project Modules Overview

* **`documents/serengeti.md`**: Serves as the static ecological knowledge base document containing detailed profiles of Serengeti wildlife, habitats, and migration patterns.
* **`memory_store.py`**: Implements the Tier 2 and Tier 3 persistence layer by managing deterministic SQLite `UPSERT` operations alongside ChromaDB vector collections.
* **`ingest.py`**: Parses and chunks the `serengeti.md` document to generate local embeddings and populate the `serengeti_knowledge` ChromaDB collection.
* **`memory_manager.py`**: Runs an asynchronous background worker powered by `gemma2` to extract user facts, update preferences, and save time-stamped episodic reflections after each conversation turn.
* **`agents.py`**: Orchestrates the multi-agent LangGraph workflow using `gemma4` to route queries, retrieve domain knowledge, and synthesize personalized responses.
* **`server.py`**: Exposes an OpenAI-compatible FastAPI backend that connects the multi-agent system to Open WebUI and triggers non-blocking memory updates.
* **`requirements.txt`**: Specifies all required local Python packages and versions needed to run the application.
* **`docker-compose.yml`**: Configures and launches the containerized Open WebUI frontend wired to the local FastAPI backend on the Mac mini host.
