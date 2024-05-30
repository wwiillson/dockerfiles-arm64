build:
	docker build --file Dockerfile . -t custom/es:6.8.23-arm64

run: build
	docker run --name es6 -p 9200:9200 -p 9300:9300 -v ./elasticsearch.yml:/usr/share/elasticsearch/config/elasticsearch.yml -d custom/es:6.8.23-arm64
