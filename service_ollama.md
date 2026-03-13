## Ollama [Native Install Service]

[Back to index](README.md)

---

**Install Ollama**
```bash
curl -fsSL https://ollama.com/install.sh | sh
```
**Open Ollama Service Config**
```bash
sudo systemctl edit ollama.service
```

**Setting as Service for all incoming IPs (local and external)**
```
[Service]
Environment="OLLAMA_HOST=0.0.0.0:11434"
```

**Pull a model**
```bash
ollama pull phi4-mini
```

**verify**
```bash
curl http://localhost:11434/api/tags
```