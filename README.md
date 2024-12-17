Support-Services-SM3
====================

This repository contains the necessary scripts, configurations, and services for **SM3 Support Services**. The project provides the infrastructure to manage various support-related operations for SM3, including automated deployments, health checks, and service monitoring.

Features
--------

-   **Automated Deployments**: Use CI/CD pipelines for easy deployment of services.
-   **Health Monitoring**: Scripts and services that ensure all critical systems are up and running.
-   **Blue-Green Deployments**: Supports zero-downtime deployments for updates and new releases.
-   **Service Switching**: Easily switch between versions using HAProxy for load balancing.

Prerequisites
-------------

-   **Docker**: Ensure Docker is installed for container management.
-   **HAProxy**: Set up for load balancing between `blue` and `green` environments.
-   **GitHub Actions**: To automate deployment pipelines and manage services efficiently.
-   **SSH Access**: SSH access to servers for deployment and maintenance tasks.
-   **Docker Hub Account**: For pushing Docker images.

Getting Started
---------------

### 1\. Clone the Repository

To start working with the repository, clone it locally:

``` bash
git clone https://github.com/yourusername/Support-Services-SM3.git
```

### 2\. Configure Environment Variables

Make sure to configure the environment variables for your specific setup. You can set them in your `.env` file or as secrets in GitHub.

### 3\. Build and Push Docker Images

You can build and push Docker images using the GitHub Actions CI pipeline.

``` bash
docker build -t yourusername/sm3-support-service:latest .
docker push yourusername/sm3-support-service:latest
```

### 4\. Deploying Services

To deploy the services to your servers, use the GitHub Actions pipeline. The pipeline will automatically handle the deployment process, including switching between the blue and green environments using HAProxy.

#### Example:

To deploy the **green** environment:

1.  Trigger the GitHub Actions pipeline with a push to the `main` branch.
2.  The pipeline will pull the latest Docker image, stop the old container, and deploy the new one.
3.  HAProxy will automatically switch traffic from the old environment (`blue`) to the new one (`green`).

### 5\. Managing HAProxy

To switch between environments manually, you can use the following script. It allows you to switch between `blue` and `green` environments:

``` bash
./switch_backend.sh [blue|green]
```

This will automatically update the HAProxy configuration and reload the service.

Contributing
------------

We welcome contributions! If you'd like to contribute to **Support-Services-SM3**, please fork the repository, make your changes, and submit a pull request.

### Steps to contribute:

1.  Fork the repository.
2.  Create a feature branch (`git checkout -b feature-branch`).
3.  Commit your changes (`git commit -m 'Add new feature'`).
4.  Push to the branch (`git push origin feature-branch`).
5.  Create a pull request.

##
© 2024 Julian Loontjens 