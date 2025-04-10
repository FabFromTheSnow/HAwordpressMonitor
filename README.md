# HA WordPress Monitor

**HA WordPress Monitor** is a comprehensive toolkit designed to monitor the performance and availability of WordPress sites. It offers configurations for various services, including Nginx, HAProxy, Filebeat, and Metricbeat, and provides a Docker Compose setup for streamlined deployment.

## Features

- **Web Server Configurations**: Includes Nginx configurations for serving WordPress sites.
- **Load Balancing**: HAProxy setup to distribute incoming traffic across multiple servers.
- **Log Shipping**: Filebeat configuration to forward logs to a centralized location for analysis.
- **Metrics Collection**: Metricbeat setup to gather system and service metrics.
- **Containerization**: Docker Compose configuration to manage and deploy services efficiently.

*Note: Apache configurations are included solely for testing purposes and are not intended for production use.*

## Repository Structure

The repository is organized into the following directories:

- **nginx/**: Contains Nginx web server configuration files.
- **haproxy/**: Includes HAProxy load balancer configuration files.
- **filebeat/**: Holds Filebeat configuration for log forwarding.
- **metricbeat/**: Contains Metricbeat configuration for metrics collection.

Additionally, the repository includes:

- **.gitignore**: Specifies files and directories to be ignored by Git.
- **docker-compose.yml**: Defines the Docker Compose configuration for deploying the services.
- **env.example**: An example environment file to set up necessary environment variables.

## Getting Started

To set up the HA WordPress Monitor, follow these steps:

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/FabFromTheSnow/HAwordpressMonitor.git
   ```

2. **Navigate to the Project Directory**:

   ```bash
   cd HAwordpressMonitor
   ```

3. **Configure Environment Variables**:

   Copy the `env.example` file to `.env` and update the environment variables as needed:

   ```bash
   cp env.example .env
   ```

   Edit the `.env` file to set your specific configuration values.

4. **Deploy with Docker Compose**:

   Ensure you have Docker and Docker Compose installed. Then, run:

   ```bash
   docker-compose up -d
   ```

   This command will start all the services defined in the `docker-compose.yml` file in detached mode.

## Contributing

Contributions are welcome! If you have suggestions for improvements or encounter issues, please open an issue or submit a pull request.

---

*Note: This README is based on the current structure and contents of the repository. For the most accurate and detailed information, please refer to the actual files and configurations within the repository.*
