# Ambrosia

Ambrosia is a digital recipe book. A bit of a pet project since I needed to digitize my own recipe collection, and couldn't find a platform I was satisfied with that could do it.

## Build, Run, Deploy

Docker all the way!

Once that is up and running, access it on [port 3000](http://localhost:3000).

### Platform x86-amd64

```bash
docker-compose build --parallel
docker stack deploy -c docker-compose.yml ambrosia
```
