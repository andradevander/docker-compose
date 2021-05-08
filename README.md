# Criando Mysql Docker

### Construindo as imagens

Acesse a pasta raíz do projeto e construa cada imagem (MySQL):

```
docker build -t mysql-image -f db/Dockerfile .
```

### Rodando os containers
Na pasta raíz do projeto, execute um de cada vez:

```
docker run -d -v $(pwd)/db/data:/var/lib/mysql --rm --name mysql-container mysql-image
```

### Agora faça o restore do banco:
```
docker exec -i mysql-container mysql -uroot -p102030 < db/script.sql
```

### Docker Compose:
```
docker-compose up -d
```
