config-server

dependencies :
	1. Config Server
	2. Eureka Discovery
	3. Actuator
	
@EnableConfigServer

server.port=8888
spring.cloud.config.server.git.uri=


localhost:8888/config-client-app/default
localhost:8888/config-client-app/prod
localhost:8888/config-client-app.properties
localhost:8888/config-client-app.yml
