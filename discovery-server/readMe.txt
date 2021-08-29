discovery-server

dependencies :
	1. Eureka server
	2. DevTools
	3. Actuator
	
@EnableEurekaServer

spring.application.name=discovery-server
eureka.client.register-with-eureka=false	
eureka.client.fetch-registry=false
server.port=8761