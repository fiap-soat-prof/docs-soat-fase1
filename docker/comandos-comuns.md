# Docker

## Comandos comuns 

### Imagens

#### List Images
```bash
docker image ls
```

#### Download Image Base
```bash 
docker image pull IMAGE_NAME:TAG

# Example
docker image pull node:18
```

#### Upload Image to a repositpory
```bash 
docker image push IMAGE_NAME:TAG

# Example
docker image push node:18
```

#### Build Image from Dockerfile
```bash 
docker image build -f DOCKERFILE_NAME DIRECTORY

# Example
docker image build -f Dockerfile .
```

#### Delete Image
```bash 
docker image rm IMAGE_NAME

# Example
docker image rm node:18
```

### Containers

#### List Containers
```bash 
docker container ls
```

#### Create Container
```bash 
docker container create IMAGE

# Example
docker container create node:18
```

#### Run Container interactive
```bash 
docker container run -it IMAGE

# Example
docker container run -it node:18
```

#### Run Container daemon
```bash 
docker container run -d IMAGE

# Example
docker container run -d node:18
```

#### Run Container to create interaction before daemon
```bash 
docker container run -dit IMAGE

# Example
docker container run -dit node:18
```

#### Run Container stats
```bash 
docker container stats CONTAINER_ID

# Example
docker container stats a1bc23ed45fg
```

#### Run Container stop
```bash 
docker container stop CONTAINER_ID

# Example
docker container stop a1bc23ed45fg
```

#### Run Container start
```bash
docker container start CONTAINER_ID

# Example
docker container start a1bc23ed45fg
```

#### Run Container pause
```bash
docker container pause CONTAINER_ID

# Example
docker container pause a1bc23ed45fg
```

#### Run Container unpause
```bash
docker container unpause CONTAINER_ID

# Example
docker container unpause a1bc23ed45fg
```

#### Run Container delete
```bash
docker container rm CONTAINER_ID

# Example
docker container rm a1bc23ed45fg
```

### Networks

#### List networks
```bash 
docker network ls
```

#### Create network
```bash 
docker network create --driver DRIVER_NAME NETWORK_NAME

# Example
docker network create --driver bridge rede-fiap
```

#### Inspect network
```bash 
docker network inspect NETWORK_NAME

# Example
docker network inspect rede-fiap
```

#### Delete network
```bash 
docker network rm NETWORK_NAME

# Example
docker network rm rede-fiap
```

### Volumes

#### List Volumes
```bash 
docker volume ls
```

#### Create volume
```bash 
docker volume create VOLUME_NAME

# Example
docker volume create disk-fiap
```

#### Inspect volume
```bash 
docker volume inspect VOLUME_NAME

# Example
docker volume inspect disk-fiap
```

#### Delete volume
```bash 
docker volume rm VOLUME_NAME

# Example
docker volume rm disk-fiap
```

### Logs

#### Show logs from a container
```bash 
docker logs CONTAINER_ID

# Example
docker logs a1bc23ed45fg
```


### Tabela de comandos

| Módulo | Comando | Função |
| ------ | ------- | ------ |
| Container | `docker container ls` | listar containers |
| Container | `docker container run IMAGE` | executa um novo container com imagem criada/base |
| Container | `docker container run -d IMAGE` | executa um novo container em segundo plano |
| Container | `docker container run -it IMAGE` | executa um novo container de forma interativa (entra na execução do app) |
| Container | `docker container run -p 8080:80 nginx`| executa um novo container fazendo o forward da porta 80 do nginx para saída 8080, nginx fica acessível no navegador via localhost:8080 |
| Container | `docker container rm -f ID/ALIAS_CONTAINER` | deleta um container em execução |
| Container | `docker container stop ID/ALIAS_CONTAINER` | para um container em execução |
| Container | `docker container start ID/ALIAS_CONTAINER` | liga um container parado |
| Container | `docker container restart ID/ALIAS_CONTAINER` | reinicia um container em execução |
| Container | `docker container pause ID/ALIAS_CONTAINER` | pausa um container em execução |
| Container | `docker container unpause ID/ALIAS_CONTAINER` | inicia novamente um container que esteja pausado |
| Container | `docker container create IMAGE` | cria um container mais não o inicia |
| Container | `docker container exec -it ID/ALIAS_CONTAINER EXECUTABLE` | executa um container interativo a partir de um executável (ex: bash) |
| Container | `docker container stats ID/ALIAS_CONTAINER` | detalha os status dos recursos usados pelo container |
| Container | `docker container top ID/ALIAS_CONTAINER` | detalha os processo em execução do container |
| Container | `docker container events ID/ALIAS_CONTAINER` | mostra em tempo real os events de um container em execução |
| Container | `docker container attach ID/ALIAS_CONTAINER` | entra dentro de um container em execução |
| Container | `docker container cp FILE_PATH ID/ALIAS_CONTAINER:CONTAINER_PATH` | copia um arquivo local para dentro do container em execução |
| Container | `docker container kill ID/ALIAS_CONTAINER` | envia um comando SIGKILL para o container em execução |
| Image | `docker image ls` | lista todas imagens locais |
| Image | `docker image pull IMAGE:TAG` | baixa uma imagem base |
| Image | `docker image push IMAGE:TAG` | envia uma imagem para o repositório |
| Image | `docker image rm IMAGE` | deleta uma imagem local |
| Image | `docker image build DIRECTORY` | builda uma imagem a partir de um Dockerfile (ex: DIRECTORY = pasta onde o Dockerfile está) |
| Image | `docker image build -f Dockerfile-teste .` | builda uma imagem indicando um arquivo Dockerfile específico na raíz |
| Image | `docker image tag IMAGE_TAG NEW_IMAGE_TAG` | altera o nome/tag de uma imagem |
| Image | `docker image commit CONTAINER_ID NEW_IMAGE_TAG` | cria uma imagem a partir de um container |
| Network | `docker network ls` | lista redes criadas |
| Network | `docker network create --driver TYPE_DRIVER NETWORK_NAME` | cria uma nova rede |
| Network | `docker network inspect NETWORK_NAME` | traz informações de uma rede |
| Network | `docker network connect NETWORK_NAME CONTAINER_ID` | anexa uma rede a um container existente |
| Network | `docker network disconnect NETWORK_NAME CONTAINER_ID` | desanexa uma rede de um container existente |
| Network | `docker network rm NETWORK_NAME` | deleta uma rede criada |
| Volume | `docker volume ls` | lista todos volumes locais |
| Volume | `docker volume create VOLUME_NAME` | cria um novo volume |
| Volume | `docker volume rm VOLUME_NAME` | deleta um volume |
| Volume | `docker volume inspect VOLUME_NAME` | traz informações sobre um volume |
| Logs | `docker container logs CONTAINER_ID` | mostra em tela logs de um container |
| Management | `docker login` | loga no Docker Hub |
| Management | `docker logout` | desloga do Docker Hub |
| Management | `docker info` | mostra informações sobre o sistema |
| Management | `docker system prune` | deleta tudo que não estiver sendo usado, imagens/container/volumes/redes.. |