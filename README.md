# Donetick_Deployment
This repo is for learning Donetick deployment

1) Make sure you installed docker and docker compose properly you can use the docker docs to install it (https://docs.docker.com/engine/install/) 

1- clone the Donetick repo on server

2- cd to /donetick directory

3- replace docker-compose.yaml with this

```
services:
  donetick:
    image: donetick/donetick
    container_name: donetick
    restart: unless-stopped
    ports:
      - 2021:2021
    volumes:
      - ./data:/donetick-data
      - ./config:/config
    environment:
      - DT_ENV=selfhosted
      - DT_SQLITE_PATH=/donetick-data/donetick.db
      
```


4) and save and exit

5) sudo docker compose up -d
