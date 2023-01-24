# learning-docker
Repositório dedicado ao aprendizado de docker,
e a fonte de conhecimento base será o [alura](https://cursos.alura.com.br).

# curso realizado
[Certificação Docker DCA - Alura](https://cursos.alura.com.br/formacao-docker-dca)
- [[C]Docker: criando gerenciando containers](https://cursos.alura.com.br/certificate/viserion77/docker-criando-gerenciando-containers)
- [[C]Docker Swarm: orquestrando containers](https://cursos.alura.com.br/certificate/viserion77/docker-swarm-cluster-container)

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
- Inspecionar container: `docker inspect {{containerId}}`
- - Formato mais legível: `--pretty` 
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

### Swarm
#### Manager
- Criar swarm: `docker swarm init`
- - Configurar endereço: `--advertise-addr {{ip}}`
- - Recriar um um bkp: `--force-new-cluster`
- Obter join token: `docker swarm join-token worker`
- - Obter somente o token: `-q`
- Listar nodes: `docker node ls`
- - Formatar listagem: `-f "{{.ID}} {{.Status.State}}"` || `--format "{{.Hostname}} {{.ManagerStatus}}"`
- Remover node: `docker node rm {{nodeId}}`
- Subindo um serviço: `docker service create {{imageName}}`
- Listar serviços: `docker service ls`
- Listar tasks: `docker service ps {{serviceId}}`
- Remover serviço: `docker service rm {{serviceId}}`
- - Remover todos os serviços: `docker service rm $(docker service ls -q)`
- Rebaixar node: `docker node demote {{nodeId}}`
- Atualizar status de um node: `docker node update {{nodeId}} --availability {{availability}}`
- Atualizar restrições de um serviço: `docker service update {{serviceId}} --constraint-add node.role=={{role}}`
- Atualizar numero de replicas de um serviço: `docker service update {{serviceId}} --replicas {{replicas}}`
- Iniciar serviço em um modo especifico: `docker service create --mode {{mode}} {{imageName}}`
- Iniciar stack de deploy: `docker stack deploy --compose-file docker-compose.yml {{stakName}}`
- Listar staks: `docker stack ls`
- Remover stak: `docker stack rm {{stackName}}`
#### Worker
- Entrar em um swarm: `docker swarm join --token {{token}} {{ip}}:{{port}}`
- Sair do swarm: `docker swarm leave`


## Sample comande

Este exemplo vai baixar uma imagem do ubuntu, apois isto vai criar um container com esta imagem e realizar um link entre a pasta atual e a pasta github no container
```bash
docker pull ubuntu
docker run -it --name ubuntu --mount type=bind,source=$(pwd),target=/github ubuntu bash
```
