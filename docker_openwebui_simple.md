## Open WebUI (Simple) [Docker]

[Back to index](README.md)

---

**Create Directory**
```bash
mkdir -p /srv/apps/openwebui
```

**Create docker-compose.yml File**
```bash
cd /srv/apps/openwebui
nano docker-compose.yml
```
**Paste, Save and Exit**
```yml
services:
  openwebui:
    image: ghcr.io/open-webui/open-webui:main
    container_name: openwebui
    restart: unless-stopped
    ports:
      - "8080:8080"
    volumes:
      - /srv/data/openwebui/data:/app/backend/data
    extra_hosts:
      - "host.docker.internal:host-gateway"
```
**Start Docker Container**
```bash
docker compose -f /srv/apps/openwebui/docker-compose.yml up -d
```
**or (since you are already in the correct directory)**
```bash
docker compose up -d
```
---