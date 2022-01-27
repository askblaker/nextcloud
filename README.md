# Nextcloud

Getting started with nextcloud.
Not recommended or tested for production, but it's a good way to quickly test.

[docker / docker-compose](https://docs.docker.com/compose/)  
[nextcloud v23](https://nextcloud.com/)
[traefik v2.5](https://traefik.io/traefik/)
[postgreSQL v14.1](https://www.postgresql.org/)  
[redis v6.2](https://redis.io/)

## Prerequisites

1. DNS A records pointing to your server (or to a load balancer)
2. Server / VPS
3. docker
4. docker-compose

## Guide

1. git clone this repository and cd into it
2. Rename .env.example to .env
3. Change the variables as you need
4. Create the needed directories

```bash
mkdir app && mkdir apps && mkdir config && mkdir db && mkdir files
```

5. Create the needed network

```bash
docker network create traefik_proxy
```

4. Run the containers:

```bash
docker-compose up -d
```

## Reset nextcloud

Note! This will delete all nextcloud data!
If you want to reset nextcloud you can delete all containers and data like this:

```bash
docker-compose down
docker volume prune
rm -rf ./app/ && rm -rf ./apps/ && rm -rf ./db/ && rm -rf ./files/ && rm -rf ./config/
mkdir app && mkdir apps && mkdir config && mkdir db && mkdir files
```
