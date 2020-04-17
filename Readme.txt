docker pull ubuntu:latest

docker pull postgres:latest

docker run -td ubuntu

docker ps

touch docker-compose.yml

nano docker-compose.yml
<в открывшемся окне вставить нижний текст в файл и сохранить>
version: '3.1'
services :
  db:
    image: postgres:10-alpine
    ports:
      - "5432:5432"
    environment:
      POSTGRES_USER: user1
      POSTGRES_PASSWORD: password
      POSTGRES_DB: tododb
  admin:
    image: adminer
    restart: always
    depends_on: 
      - db
    ports:
      - 8080:8080

docker-compose up -d

docker run -d \
> -e POSTGRES_PASSWORD=mysecretpassword \
> postgres

docker ps




