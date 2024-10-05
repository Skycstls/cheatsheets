# Docker

## Configuración

Añadir el repositorio de Docker:

```bash
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

Instalar Docker:

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

Iniciar, habilitar el servicio y añadir el usuario al grupo `docker` para evitar el uso de `sudo`:

```bash
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -aG docker $USER
```

Hello World:

```bash
sudo docker run hello-world
```

## Comandos

```bash
docker build -t <image-name> .        # Construye una imagen a partir de un Dockerfile
docker images                         # Lista las imágenes
docker run -d <image-name>            # Ejecuta la imagen
docker run -d -p 8080:80 <image-name> # Mapea host:8080 a docker:80
docker ps                             # Lista los contenedores en ejecución
docker ps -a                          # Lista todos los contenedores
docker stop <container-id>            # Detiene un contenedor
docker rm <container-id>              # Elimina un contenedor
docker rmi <image-id>                 # Elimina una imagen
```

## Contenedores

```bash
docker exec -it <container-id> /bin/bash        # Abrir una terminal en un contenedor en ejecución
docker logs <container-id>                      # Muestra los logs de un contenedor
docker inspect <container-id>                   # Muestra información detallada de un contenedor
docker cp <container-id>:/path/to/file .        # Copia un archivo desde un contenedor a la máquina host
docker cp file.txt <container-id>:/path/to/file # Copia un archivo desde la máquina host a un contenedor
docker inspect -f '{{.NetworkSettings.IPAddress}}' <container-id> # Muestra la IP de un contenedor
docker inspect <container-id> | grep IPAddress  # Muestra la IP de un contenedor
```

## Dockerfile

```Dockerfile
docker build -t <image-name> . # Construye una imagen a partir de un Dockerfile
docker-compose up -d           # Levanta los servicios definidos en el archivo docker-compose.yml en segundo plano
docker-compose down            # Detiene y elimina los servicios definidos en el archivo docker-compose.yml
```

### Sintaxis

```plaintext
FROM      # Establece la imagen base
WORKDIR   # Establece el directorio de trabajo
COPY      # Copia archivos o directorios al contenedor
RUN       # Ejecuta comandos en el contenedor
CMD       # Ejecuta comandos al iniciar el contenedor
EXPOSE    # Expone un puerto del contenedor al host
```

```Dockerfile
FROM node:14
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "start"]
```
