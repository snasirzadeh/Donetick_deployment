# Donetick_Deployment
This repo is for learning Donetick deployment

1) Make sure you installed docker and docker compose properly you can use the docker docs to install it 

https://docs.docker.com/engine/install/ 

2) clone the Donetick repo on server

3) cd to /donetick directory

4) Use this template to set up Donetick with Docker compose or replace it with docker-compose.yaml

```
services:
  donetick:
    image: donetick/donetick
    container_name: donetick
    restart: unless-stopped
    ports:
      - "127.0.0.1:2021:2021"
    volumes:
      - ./data:/donetick-data
      - ./config:/config
    environment:
      - DT_ENV=selfhosted
      - DT_SQLITE_PATH=/donetick-data/donetick.db
      
```
5) At the end type this command

```
docker compose up -d
```





