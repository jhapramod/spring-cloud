service
dependencies :
	1. Eureka Discovery
	2. DevTools
	3. Actuator
	4. Spring Web
	
@EnableDiscoveryClient
@RestController

@Value("{service.instance.name}")
private String instance

@RequestMapping
public String message() {
	return "Hello from " + instance
}


spring.application.name=service
eureka.client.service-url.defaultZone=http://localhost:8761/eureka

server.port=8081
service.instance.name=instance-1

server.port=8081
service.instance.name=instance-1