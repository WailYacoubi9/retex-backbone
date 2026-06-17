# retex-backbone

Services partages du projet RETEX : **Neo4j** (graphe), **Qdrant** (vecteurs),
**Ollama** (embeddings + LLM). Crée le réseau Docker `retex-net` que
`retex-app` et `retex-ingestion` rejoignent.

## Démarrer
```bash
docker compose up -d
docker compose ps
```

## Modèles Ollama (une fois)
```bash
docker exec retex-ollama ollama pull qwen2.5:7b
docker exec retex-ollama ollama pull bge-m3
```

## Sans GPU
Supprimer le bloc `deploy:` (réservation NVIDIA) du service `ollama` dans
`docker-compose.yml` → Ollama tourne en CPU (plus lent).

## Accès
- Neo4j Browser : http://localhost:7474 (neo4j / retex_dev_pwd)
- Qdrant : http://localhost:6333
- Ollama : http://localhost:11434
