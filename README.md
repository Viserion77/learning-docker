# learning-docker
Repositório dedicado ao aprendizado de docker,
e a fonte de conhecimento base será o [alura](https://cursos.alura.com.br).

# curso realizado
[Certificação Docker DCA - Alura](https://cursos.alura.com.br/formacao-docker-dca)
- [[C]Docker: criando gerenciando containers](https://cursos.alura.com.br/certificate/viserion77/docker-criando-gerenciando-containers)

## Comando uteis para docker

- Validar instalação: `docker --version`

### Images
- Baixar imagem: `docker pull {{imageName}}`
- Listar imagens: `docker images`
- Remover imagem: `docker rmi {{imageName}}`
- - Remover todas as imagens: `docker rmi $(docker images -aq) --force`
- Compilar imagem: `docker build .`
- - Adicionar apelido: `-t {{imageName}}`

### Containers
- Executar container: `docker run {{imageName}}` || `docker start {{containerId}}`
- - Container interativo: `-i`
- - Terminal virtual: `-t`
- - Executar em background: `-d`
- - Expor portas: `-P` || `-p {{hostPort}}:{{containerPort}}`
- - Lincar diretórios: `-v {{hostPath}}:{{containerPath}}` || `--mount type=bind,source={{hostPath}},target={{containerPath}}`
- inspecionar container: `docker inspect {{containerId}}`
- Listar containers: `docker ps` || `docker container ls`
- - Containers encerrados: `-a`
- - Retornar somente ids: `-q`
- - Tamanho do container: `-s`
- Remover container: `docker rm {{containerId}}`
- - Remover todos os containers: `docker rm $(docker ps -qa)`
- Parar container: `docker stop {{containerId}}`
- Executar terminal do container: `docker exec -it {{containerId}} bash`

### Volumes
- Listar volumes: `docker volume ls`
- Criar volume: `docker volume create {{volumeName}}`

### Networks
- Listar redes: `docker network ls`
- Criar rede: `docker network create {{networkName}}`


## Sample comande
```bash
docker run -it --name Ubuntu --mount type=bind,source=$(pwd),target=/github ubuntu bash
```
