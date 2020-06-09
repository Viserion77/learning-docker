# learning-docker
Aprendendo Docker

Comands
Cria imagem na raiz do projeto
`$ docker build -t mysql-image -f api/db/DockerFile .` 
Lista as imagens
`$ docker image ls `
-d: terminal não fica preso no contexto
-- rm remove e cria um novo
`$ docker run -d --rm --name mysql-container mysql-image`
Ver os containers
`$ docker ps`