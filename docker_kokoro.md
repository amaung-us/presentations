## Kokoro TTS [Docker]

[Back to index](README.md)

---

**Create Directory**
```bash
mkdir -p /srv/apps/kokoro
```

**Create docker-compose.yml File**
```bash
cd /srv/apps/kokoro
nano docker-compose.yml
```
**Paste, Save and Exit (Pick One)**

For low useage, recommend using CPU -- no point eating up GPU RAM and cycles
```yml
services:
  kokoro:
    image: ghcr.io/remsky/kokoro-fastapi-cpu:latest
    container_name: kokoro
    restart: unless-stopped
    ports:
      - "8880:8880"
```
NVidia GPU
```yml
services:
  kokoro:
    image: ghcr.io/remsky/kokoro-fastapi-gpu:latest
    container_name: kokoro
    restart: unless-stopped
    ports:
      - "8880:8880"
```
**Start Docker Container**
```bash
docker compose -f /srv/apps/kokoro/docker-compose.yml up -d
```
**or (since you are already in the correct directory)**
```bash
docker compose up -d
```
---