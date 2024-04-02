Jobs Reviews on Companies Microservices

This project is a platform designed to facilitate job seekers in reviewing companies'. It aims to provide a space for users to share their experiences, rate companies based on their microservices, and offer insights that can help others in their job search.

Features

- User authentication and profiles
- Company profiles with microservices reviews
- Rating system for reviews
- Search functionality for companies and reviews

Technologies Used

- Spring Boot: For building the microservices.
- Spring Cloud: For implementing microservices architecture patterns.
- Spring Security: For securing the application.
- Spring Data JPA: For database access and management.
- PostgreSQL: As the database for storing user profiles, company profiles, and reviews.
- Docker: For containerization of the microservices.
- Kubernetes: For orchestration of the microservices in a containerized environment.

Installation and Setup

1. Clone the repository: `git clone https://github.com/felixojiambo/Jobs_Reviews_OnCompanies.git`
2.Navigate to the project directory: `cd Jobs_Reviews_OnCompaniesMicroservices`
3.Initialize and update submodules: Run `git submodule update --init --recursive` to clone the submodules.
4. Build the project: `./mvnw clean install` (This command builds the project and runs tests. Adjust if your project uses a different build tool.)
5. Run the application: You can run the application using Spring Boot's Maven plugin with `./mvnw spring-boot:run` or by running the main class in your IDE

Usage
To use the platform, visit the deployed website and sign up or log in. You can then browse companies, read reviews, and submit your own reviews.

Contributing

Contributions are welcome! Please read the [contributing guidelines](CONTRIBUTING.md) before getting started.

License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
