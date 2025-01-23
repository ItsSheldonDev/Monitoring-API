# Monitoring API

Simple API to monitor web services status.

## Features
- Check service status
- Get response times
- Monitor multiple endpoints
- Service history
- Rate limiting and security

## Configuration
Place config.json in monitoring folder:
```json
{
  "services": [
    {
      "name": "example",
      "url": "https://example.com"
    }
  ]
}
```

## Docker
```bash
docker run -d \
  -p 3000:3000 \
  -v /path/to/config.json:/app/config.json \
  sheldondev/monitoring-api
```

## Docker Compose
```yaml
version: "3.8"
services:
  monitoring-api:
    image: sheldondev/monitoring-api
    container_name: monitoring-api
    volumes:
      - /opt/stacks/network_local/monitoring/config.json:/app/config.json
    ports:
      - "3000:3000"
    restart: unless-stopped
```

## API Endpoints
```
- GET /check/:service - Check specific service
```