Jobs_Reviews_OnCompanies Microservices Project

Welcome to the Zep Microservices Project, a comprehensive architecture designed to manage reviews, jobs, and companies within a larger system. This project leverages Spring Boot for microservices development, Spring Cloud for service discovery and configuration, and includes an API Gateway for request routing.

**Kindy Note:**
When using Kubernetes, the need for a service discovery tool like Eureka and an API gateway can indeed be reduced or even eliminated, thanks to Kubernetes' built-in features and the ecosystem of tools available. Let's explore how Kubernetes can replace these components and why.

### Service Discovery with Kubernetes

Kubernetes provides a native service discovery mechanism through its DNS service. Each service in Kubernetes has a DNS name that is automatically resolved to the IP address of the service. This DNS name follows the format `<service-name>.<namespace>.svc.cluster.local`, where `<service-name>` is the name of the service and `<namespace>` is the namespace in which the service resides. This DNS resolution is handled by the kube-dns or CoreDNS service running in the cluster, depending on your Kubernetes version.

#### Example:

Suppose you have a service named `my-service` in the `default` namespace. Pods within the same namespace can access this service using the DNS name `my-service.default.svc.cluster.local`.
Kubernetes

There  are several solutions available that can be integrated into your Kubernetes cluster to provide API gateway functionality. One popular choice is Ambassador, which is an open-source Kubernetes-native API Gateway built on Envoy Proxy. Ambassador can handle routing, load balancing, and other API gateway features like authentication, rate limiting, and more.

#### Example:

To set up Ambassador as an API gateway in the Kubernetes cluster, you would typically follow these steps:

1. **Install Ambassador**: You can install Ambassador using Helm, the package manager for Kubernetes.

    ```bash
    helm repo add datawire https://www.getambassador.io
    helm install ambassador datawire/ambassador
    ```

2. **Configure Routes**: Define your API routes in Kubernetes resources. Ambassador will automatically discover these routes and configure the gateway accordingly.

    ```yaml
    apiVersion: getambassador.io/v2
    kind: Mapping
    metadata:
      name: my-service-mapping
    spec:
      prefix: /my-service/
      service: my-service.default.svc.cluster.local:8080
    ```

3. **Access Your Services**: With Ambassador running and configured, we can access your services through the API gateway using the configured routes.

### Conclusion

By leveraging Kubernetes' native service discovery and integrating an API gateway solution like Ambassador, we can achieve similar functionality to what Eureka and an API gateway provide in a traditional microservices architecture. This approach simplifies service discovery and API management, making it easier to scale and manage your applications in a Kubernetes environment.
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
