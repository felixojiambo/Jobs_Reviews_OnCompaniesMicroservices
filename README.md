Jobs_Reviews_OnCompanies Microservices Project

Welcome to the Zep Microservices Project, a comprehensive architecture designed to manage reviews, jobs, and companies within a larger system. This project leverages Spring Boot for microservices development, Spring Cloud for service discovery and configuration, and includes an API Gateway for request routing.

Project Structure

The project is structured into four main components:

Reviews Microservice: Handles reviews for companies, offering CRUD operations and average rating calculation.
Jobs Microservice: Manages job listings, providing CRUD operations.
Company Microservice: Manages company information, offering CRUD operations.
API Gateway: Acts as the entry point for all client requests, routing them to the appropriate microservice.
Additionally, the project includes a Config Server for centralized configuration management and a Service Registry (Eureka Server) for service discovery.

Key Features

RabbitMQ Integration: Asynchronous messaging between microservices for decoupled communication.
Feign Client: Simplifies HTTP client development for inter-service communication.
Centralized Configuration: Config Server provides centralized configuration management.
Service Discovery: Eureka Server facilitates service discovery and registration.
Running the Project

To run the project, start the Config Server, Service Registry (Eureka Server), API Gateway, and the individual microservices (Reviews, Jobs, Company). Each component can be started independently using Spring Boot's SpringApplication.run() method.

Conclusion

The Zep Microservices Project showcases a scalable and maintainable microservices architecture using Spring Boot and Spring Cloud. It demonstrates how to build, deploy, and manage microservices in a cloud-native environment, including asynchronous messaging with RabbitMQ, inter-service communication with Feign, and centralized configuration management with Spring Cloud Config.
