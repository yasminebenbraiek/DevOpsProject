# Multimedia Library API Microservices Project with DevOps Integrations

## Overview

This Node.js-based project focuses on developing a Microservices Architecture to create a Multimedia Library API. The system allows efficient management of diverse content types, including books, magazines, and audiovisual materials, through a centralized API Gateway. Clients can interact with the system using both RESTful and GraphQL endpoints, enabling CRUD operations on library resources.

## Key Features

- **Microservices Architecture:** Utilizes gRPC for efficient communication, with each microservice dedicated to managing specific content types.
  
- **API Gateway:** Serves as a centralized entry point, facilitating seamless integration and data management between clients and microservices.
  
- **RESTful and GraphQL Endpoints:** Offers flexibility in data retrieval and manipulation for clients.
  
- **Simple Frontend:** Includes a straightforward frontend for testing and interacting with REST clients, enhancing the development experience.

## Microservices and Data Management

- **gRPC Framework:** Microservices are built using the gRPC framework, ensuring a modular and scalable approach to handling multimedia library resources.

- **Database:** Utilizes an SQLite3 database for storing data related to books, magazines, and audiovisual materials. The database is automatically managed by the microservices.

## Git Repository Setup

### Repository Content

- The repository contains:
  - Codebase for the entire project.
  - Jenkinsfile defining the CI/CD pipeline.
  - Dockerfiles for the microservices.
  - Docker-compose file.
  - Kubernetes objects in simple manifests.

## Jenkins Pipeline

### Pipeline Overview

- The Jenkins pipeline automates the CI/CD process with the following aspects:

  - **Initialization of Global Variables:** Global variables needed for the pipeline are initialized.
  
  - **Build Image:** Docker images are built, encapsulating application components.
  
  - **Testing:** Conducts unit or integration testing for application functionality and integrity.
  
  - **Image Registry Push:** Pushes built Docker images to a container registry: DockerHub.
  
  - **Cleanup:** Post-deployment cleanup activities to ensure a clean environment.

## Kubernetes Deployment

### Kubernetes Objects

- The project includes at least two Kubernetes objects:

  - **RollingUpdate Deployment:** Implements a deployment strategy with a replicaset of 5 instances for smooth updates.
  
  - **NodePort Service:** A service of type NodePort for testing on Minikube.
  
  - **LoadBalancer Service:** A service of type LoadBalancer.


**In summary**, this project follows a comprehensive CI/CD process with Dockerfiles, Jenkins pipeline, incorporates Kubernetes deployment with RollingUpdate strategy and services like NodePort and LoadBalancer.
