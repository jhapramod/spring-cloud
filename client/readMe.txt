client

dependencies :
	1. Eureka Discovery
	2. DevTools
	3. Actuator
	4. Spring Web
	
@EnableDiscoveryClient
@RestController

@Autowired
private EurekaClient client;

@Autowired
private RestTemplateBuilder restTemplateBuilder


@RequestMapping("/")
public String callService() {
	RestTemplate restTemplate = new RestTemplateBuilder.build();
	InstanceInfo instanceInfo = client.getNextServerFromEureka("service", false);
	String baseUrl = instanceInfo.getHomePage();
	ResponseEntity<String> response = restTemplate.exchange(baseUrl, HttpMethod.get, null, String.class);
	return response.getBody();
	
}


spring.application.name=client
eureka.client.register-with-eureka=false
eureka.client.service-url.defaultZone=http://localhost:8761/eureka