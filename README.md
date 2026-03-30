#n8n Agent Builder
Convert a chat request into a complete n8n workflow template with AI agents and rag

Run these commands to launch n8n docker 
bash
docker volume create n8n data 

docker run -it --rm \
 --name n8n \
 -p 5678:5678 \
 -e N8N_ENFORCE_SETTINGS_FILE_PERMISSIONS=true \
 -e N8N_RUNNERS_ENABLED=true \
 -v n8n_data:/home/node/.n8n \
 docker.n8n.io/n8nio/n8n

##Open http://localhost:5678.
import the provided JSON file app.json

listens to requests  Chat trigger

R searches the web SerpAPI and n8n docs Pinecone rag

generate GPT4o or Ollama designs nodes and validates JSON

Deliver Provides a downloadable .json file for immediate import

Required API credentials

Service	Credential  Setup

OpenAI  Ollama	Use OpenAI API node. Set Base URL to: http://docker.internal
Pinecone	Vector Database for RAG.

OpenRouter	GPT-4o LLM access.

SerpAPI	Web Search capability.

Firecrawl	Optional for URL crawling.

Running with Ollama

To use a local model instead of OpenAI:

ensure Ollama is running on your host machine.

in the n8n OpenAI Chat Model node toggle base url

enter your Ollama server address usually http://docker.internal for Docker users

enter any placeholder text for the API Key Ollama does not require one by default
