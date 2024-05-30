## Custom Elasticsearch
- build for version 6.8.x
- uses Amazon corretto 8
- works with Mac M1

## Build
```bash
make build
```

## Run standalone
- Runs with no auth and no https
- See [elasticsearch.yml](elasticsearch.yml)

```bash
make run
```

## Docker compose
- Runs with no auth and no https
- See [elasticsearch.yml](elasticsearch.yml)
- See [docker-compose.yml](docker-compose.yml)

```bash
docker-compose up -d
```