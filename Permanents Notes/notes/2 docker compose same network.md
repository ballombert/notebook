---
tags: docker-compose
---
Create a network :

```bash
$ docker network create external-example
```

First docker compose

```yaml
version: '3' 
services: 
  service1: 
    image: busybox 
    command: sleep infinity 

networks: 
  default: 
    external: 
      name: external-example
```


Second docker compose

```yaml
version: '3' 
services: 
  service2: 
    image: busybox 
    command: sleep infinity 

networks: 
  default: 
    external: 
      name: external-example
```