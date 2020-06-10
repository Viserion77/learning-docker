# learning-docker
Aprendendo Docker

Comandos para criçãodo docker...

criar arquivo DockerFile dentro de api/db

Cria imagem na raiz do projeto
`$ docker build -t mysql-image -f api/db/DockerFile .`

Lista as imagens
`$ docker image ls `

Executa a imagem subindo container
-d: terminal não fica preso no contexto
--rm: remove e cria um novo
--name nomeia o container
`$ docker run -d --rm --name mysql-container mysql-image`

Ver os containers
`$ docker ps`
