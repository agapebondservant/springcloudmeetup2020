## Demonstration of Spring Cloud with Consul and Resilience4j

### Overview
This is a *suuuper* basic Voter Dashboard app that aggregates real-time data from 2 separate teams ("Red" squad and "Blue" squad) and displays it in a visualization. The microservices collect voting data and send it to the front-end app via an API Gateway. To do this, it utilizes:

 - Spring Webflux for reactive web API;
 - Spring Cloud Consul Discovery for service discovery;
 - Spring Cloud Loadbalancer for client-side loadbalancing;
 - Spring Cloud CircuitBreaker + Resilience4j for circuit-breaking;
 - Spring Cloud Gateway for API Gateway.

Other enhancements that can be easily introduced:

 - Spring Cloud Config for externalized configuration;
 - Spring Cloud Sleuth & Spring Cloud Zipkin for distributed tracing;
 - Spring Cloud Rabbit for messaging;
 - etc...

### How to run

 - After cloning, execute the following from the root:
 ```
 git submodule init
 git submodule update
 ```
 - Download and run **consul**:
 
	 - Use the download instructions provided [here](https://www.consul.io/downloads.html) to download the consul binary to your local machine.
	 - Use the instructions provided [here](https://learn.hashicorp.com/consul/getting-started/install) to install consul.
	 - Start a consul agent in server mode: ```consul agent -server=true -bootstrap=true -client=0.0.0.0 -ui -data-dir=/tmp/consul```
	 - Verify that it's running by going [here](http://localhost:8500) on your browser.
	 
 4. Cd into the root directories for each submodule and run ```./mvnw spring-boot:run``` to start the service.
 
 5. Navigate to [this link](http://localhost:8000) on your browser. The dashboard app should be shown with data populating.

