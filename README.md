# Ambrosia

Ambrosia is a digital recipe book. A bit of a pet project since I needed to digitize my own recipe collection, and couldn't find a platform I was satisfied with that could do it.

## Build, Run, Deploy

Docker all the way!

Once that is up and running, access it on [port 3000](http://127.0.0.1:3000).

### Build for Production
```bash
docker stack deploy -c docker-compose.yml ambrosia
```

### Build for Local Testing
```bash
docker-compose build --parallel
docker-compose up
```

### Open Firewall Ports
Assumes that you use firewalld
```bash
cp firewall-rules.xml /etc/firewalld/services/ambrosia.xml

firewall-cmd --reload
firewall-cmd --zone=public --add-service=ambrosia --permanent
firewall-cmd --reload
```
