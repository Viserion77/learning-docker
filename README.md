# learning-docker
Repositório dedicado ao aprendizado de docker,
e a fonte de conhecimento base será o [alura](https://cursos.alura.com.br).

# curso realizado
[Certificação Docker DCA - Alura](https://cursos.alura.com.br/formacao-docker-dca)

## Comando uteis para docker

- Validar instalação: `docker --version`
- Baixar imagem: `docker pull {{imageName}}`
- Listar imagens: `docker images`
- Executar container: `docker run {{imageName}}`
- - Container interativo: `-i`
- - Terminal virtual: `-t`
- Listar containers: `docker ps`
- - Containers encerrados: `-a`
- - Retornar somente ids: `-q`
- Remover container: `docker rm {{containerId}}`
- - Remover todos os containers: `docker rm $(docker ps -qa)`
- Compilar imagem: `docker build .`
- - Adicionar apelido: `-t {{imageName}}`
