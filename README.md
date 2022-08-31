jdk 11
spring-boot 2.7.2
## 도커 이미지 생성
docker build -t askyclear/config-service:1.0 .

## 도커 실행 및 rabbitmq 연동 
spring.rabbitmq.host 에 브릿지 네트워크에 등록된 rabbitmq의 ip를 입력해도 되지만 컨테이너 이름 넣어줘도 
docker run -d -p 8888:8888 --network ecommerce-network \
-e "spring.rabbitmq.host=rabbitmq" \
-e "spring.profiles.active=default" \
--name config-service askyclear/config-service:1.0

## 도커 실행 로그
docker logs