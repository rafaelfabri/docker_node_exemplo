# Aplicação Node com Docker 

## Sem Network

```bash     
docker run -d --rm -p 27017:27017 --name mongodb --network nodeapi mongo
```

```bash     
docker run -d --rm -p 80:80 --name backend --network nodeapi rafaelfabri/backend_node:1.2
```

```bash     
docker run  -p 3000:3000 --rm --name frontend --network nodeapi --it rafaelfabri/frontend_node:1.1

## Com network

```bash     
docker network nodeapi
```

```bash     
docker run -d --rm --name mongodb --network nodeapi mongo
```

```bash     
docker run -d -p 80:80     --rm --name backend  --network nodeapi rafaelfabri/backend_node:1.2
```

```bash     
docker run    -p 3000:3000 --rm --name frontend --it rafaelfabri/frontend_node:1.1
```bash



## Com network e volumes

```bash
docker run -d --rm -p 27017:27017 --name mongodb --network nodeapi -v backup_mongo:/data/db mongo
```

```bash
docker run --rm --name backend --network nodeapi -v "/home/rafaelfabrichimidt/Documentos/cursos/Learn_Docker_Docker_Compose_Deploy_Kubernetes/volume_5/multi-01-starting-setup/backend/":/app -v /app/node_modules rafaelfabri/backend_node:1.2
```


```bash     
docker run -p 3000:3000 --rm --name frontend --network nodeapi -v /home/rafaelfabrichimidt/Documentos/cursos/Learn_Docker_Docker_Compose_Deploy_Kubernetes/volume_5/multi-01-starting-setup/frontend:/app -v /app/node_modules rafaelfabri/frontend_node:1.1
```
