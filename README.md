# Ambrosia

Ambrosia is a digital recipe book. A bit of a pet project since I needed to digitize my own recipe collection, and couldn't find a platform I was satisfied with.

## Build, Run, Deploy

Docker all the way!

Stack is:
* **Client** is a vue.js app that runs on a nginx server bound to port 3000. It passes requests to `/api` that get proxied off to the server.
* **Server** is a go app that wraps up the database.

### Build and Run
```bash
docker-compose build --parallel
docker stack deploy -c docker-compose.yml ambrosia
```

### Open Firewall Ports
Assumes that you use firewalld
```bash
cp firewall-rules.xml /etc/firewalld/services/ambrosia.xml

firewall-cmd --reload
firewall-cmd --zone=public --add-service=ambrosia --permanent
firewall-cmd --reload
```
