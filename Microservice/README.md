# Microservice https://blog.pjjop.org/build-microservice-on-docker-container/
```
ดังนั้นในการออกแบบ Microservice ที่ดี เราจะยึดหลัก 2 ประการ คือ
Loosely Coupling แต่ละ Service มีหน้าที่ทำงานเพียงอย่างเดียว และควรขึ้นกับ Service อื่นให้น้อยที่สุด
High Cohesion ภายในแต่ละ Service จะมีงานที่ร่วมกันทำตามเป้าหมาย
```

```
docker-compose down --rmi all
```

## nginx
```
cd nginx-proxy
docker network create nginx-proxy
docker-compose up -d
docker-compose ps
```

## portainer
```
cd port_dock
docker-compose up -d
docker-compose ps
http://portainer.boriphuth.thddns.net
http://portainer.ec2-3-8-185-42.eu-west-2.compute.amazonaws.com
```

## RabbitMQ
```
cd mq_dock
docker network create microservice_network
docker-compose up -d
docker-compose ps
```

## Register Gateway
```
cd register_gateway_dock
docker-compose build
docker-compose up -d
docker-compose ps
```
## Student Service
```
cd student_dock
docker-compose down --rmi all
docker network create student_network
docker network ls
docker-compose build
docker-compose up -d
docker-compose ps
```

## Enroll Service
```
cd enroll_dock
docker-compose down --rmi all
docker network create enroll_network
docker-compose build
docker-compose up -d
docker-compose ps
```

## Email Service
```
cd email_dock
docker-compose down --rmi all
docker network create email_network
docker-compose build
docker-compose up -d
docker-compose ps

```

http://ec2-3-8-185-42.eu-west-2.compute.amazonaws.com:7001/docs