# Docker_Labs
## Flow
![1](https://user-images.githubusercontent.com/128603198/229380765-d44d2b00-b389-4d25-9061-30e720052aee.png)

## Solution As A Command
``` bash
docker network create anubis_network
docker run -it --name container1 --network my-bridge-network ubuntu
docker run -it --name container2  --network my-bridge-network ubuntu
```

## To Verify > Test Connectivity
``` bash
ping container2
```

## Solution As A Docker Compose >> In docker-compose.yaml file

``` yaml
version: '3'
services:
  container1:
    image: ubuntu
    container_name: container1
    networks:
      - my-bridge-network
  container2:
    image: ubuntu
    container_name: container2
    networks:
      - my-bridge-network
networks:
  my-bridge-network:
    driver: bridge
```

## To Verify
``` bash
docker-compose up
docker exec -it container1 bash
ping container2
docker-compose down

```
