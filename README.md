docker network nodeapi

docker run -d --rm --name mongodb --network nodeapi -v backup_mongo:/data/db mongo

docker run --rm --name backend --network nodeapi rafaelfabri/backend_node:1.2

docker run  -p 3000:3000 --rm --name frontend --network nodeapi rafaelfabri/frontend_node:1.1


docker run --rm --name backend --network nodeapi -v "/home/rafaelfabrichimidt/Documentos/cursos/Learn_Docker_Docker_Compose_Deploy_Kubernetes/volume_5/multi-01-starting-setup/backend/":/app -v /app/node_modules rafaelfabri/backend_node:1.2


docker run -p 3000:3000 --rm --name frontend --network nodeapi -v /home/rafaelfabrichimidt/Documentos/cursos/Learn_Docker_Docker_Compose_Deploy_Kubernetes/volume_5/multi-01-starting-setup/frontend:/app -v /app/node_modules rafaelfabri/frontend_node:1.1

