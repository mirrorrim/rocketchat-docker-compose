# rocketchat-docker-compose

## Usage

##### Create a new docker network:

```bash
docker network create traefik-public
```

##### Create acme.json file

This file will be used to store letsencrypt data.

```bash
cd ~/
touch acme.json
chmod 600 acme.json
```

##### Clone repository

```bash
git clone https://github.com/mirrorrim/rocketchat-docker-compose.git rocketchat
```

##### Create and populate .env file

```bash
cd rocketchat
cp .env.sample .env
```

##### Start rocketchat

```bash
docker-compose up -d
```

##### Dump

```bash
docker exec mongo sh -c 'mongodump --archive --gzip' > db.dump
```

##### Restore

```bash
docker exec -i mongo sh -c 'mongorestore --archive --drop --gzip' < db.dump
```
