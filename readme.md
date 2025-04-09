#This doc was written with copilot and is not meant to be exhaustive

```markdown name=README.md
# Rev2Load2xApache

A containerized web infrastructure demonstrating load balancing between two WordPress instances with comprehensive monitoring via the Elastic Stack.

## Overview

Rev2Load2xApache provides a complete environment with:

- HAProxy load balancer distributing traffic between WordPress instances
- Nginx as a frontend web server
- Dual WordPress instances sharing a common MariaDB database
- Complete Elastic Stack (Elasticsearch, Kibana, Filebeat, and Metricbeat) for monitoring

## Prerequisites

- Docker and Docker Compose installed on your system
- At least 4GB of RAM available for all containers
- Basic understanding of web servers and containerization
- Git to clone the repository

## Quick Start

1. Clone the repository:
   ```bash
   git clone https://github.com/FabFromTheSnow/Rev2Load2xApache.git
   cd Rev2Load2xApache
   ```

2. Create a `.env` file with the following variables:
   ```
   nginxportOUT=80           # External port for Nginx
   nginxportIN=80            # Internal port for Nginx
   WORDpass=your_secure_password  # Password for WordPress and MariaDB
   elasticpassword=your_elastic_password  # Password for Elastic Stack
   STACK_VERSION=8.6.0       # Version of Elastic Stack to use
   ```

3. Create the required directories for logs:
   ```bash
   mkdir -p log/nginx log/haproxy
   ```

4. Start the containers:
   ```bash
   docker-compose up -d
   ```

5. Access the components:
   - WordPress: http://localhost:[nginxportOUT]
   - Kibana Dashboard: http://localhost:5601

## Architecture

The infrastructure consists of the following components:

### Web Tier
- **Nginx**: Front gateway web server
- **HAProxy**: Load balancer with round-robin algorithm

### Application Tier
- **WordPress**: Two identical WordPress containers sharing the same content

### Database Tier
- **MariaDB**: Database server for WordPress applications

### Monitoring
- **Elasticsearch**: Core search and analytics engine
- **Kibana**: Dashboard and visualization platform
- **Filebeat**: Log shipper for Nginx and HAProxy logs
- **Metricbeat**: Metrics collector for system and container stats

## Network Structure

Four isolated Docker networks:
- **expose** (10.0.0.0/24): External-facing network
- **front** (10.0.1.0/24): Frontend network
- **back** (10.0.2.0/24): Backend network
- **bdd** (10.0.3.0/24): Database network

## Monitoring

Access Kibana at http://localhost:5601 with:
- Username: elastic
- Password: [value from elasticpassword in .env]

Available metrics include:
- Nginx access and error logs
- HAProxy traffic distribution metrics
- System and container performance metrics

## Troubleshooting

Common troubleshooting steps:
- Verify containers: `docker-compose ps`
- Check logs: `docker-compose logs [service_name]`
- Inspect networks: `docker network inspect [network-name]`

## Data Persistence

Data is persisted using Docker volumes:
- WordPress content
- MariaDB database
- Elasticsearch data
- Kibana configuration
- SSL certificates

## License

MIT

---
Created by: FabFromTheSnow
Last Updated: 2025-04-09 13:42:11 UTC
```

To push this README to your repository, follow these steps:

1. First, create the README.md file with the content above:

```bash
cat > README.md << 'EOL'
# Rev2Load2xApache

A containerized web infrastructure demonstrating load balancing between two WordPress instances with comprehensive monitoring via the Elastic Stack.

## Overview

Rev2Load2xApache provides a complete environment with:

- HAProxy load balancer distributing traffic between WordPress instances
- Nginx as a frontend web server
- Dual WordPress instances sharing a common MariaDB database
- Complete Elastic Stack (Elasticsearch, Kibana, Filebeat, and Metricbeat) for monitoring

## Prerequisites

- Docker and Docker Compose installed on your system
- At least 4GB of RAM available for all containers
- Basic understanding of web servers and containerization
- Git to clone the repository

## Quick Start

1. Clone the repository:
   ```bash
   git clone https://github.com/FabFromTheSnow/Rev2Load2xApache.git
   cd Rev2Load2xApache
   ```

2. Create a `.env` file with the following variables:
   ```
   nginxportOUT=80           # External port for Nginx
   nginxportIN=80            # Internal port for Nginx
   WORDpass=your_secure_password  # Password for WordPress and MariaDB
   elasticpassword=your_elastic_password  # Password for Elastic Stack
   STACK_VERSION=8.6.0       # Version of Elastic Stack to use
   ```

3. Create the required directories for logs:
   ```bash
   mkdir -p log/nginx log/haproxy
   ```

4. Start the containers:
   ```bash
   docker-compose up -d
   ```

5. Access the components:
   - WordPress: http://localhost:[nginxportOUT]
   - Kibana Dashboard: http://localhost:5601

## Architecture

The infrastructure consists of the following components:

### Web Tier
- **Nginx**: Front gateway web server
- **HAProxy**: Load balancer with round-robin algorithm

### Application Tier
- **WordPress**: Two identical WordPress containers sharing the same content

### Database Tier
- **MariaDB**: Database server for WordPress applications

### Monitoring
- **Elasticsearch**: Core search and analytics engine
- **Kibana**: Dashboard and visualization platform
- **Filebeat**: Log shipper for Nginx and HAProxy logs
- **Metricbeat**: Metrics collector for system and container stats

## Network Structure

Four isolated Docker networks:
- **expose** (10.0.0.0/24): External-facing network
- **front** (10.0.1.0/24): Frontend network
- **back** (10.0.2.0/24): Backend network
- **bdd** (10.0.3.0/24): Database network

## Monitoring

Access Kibana at http://localhost:5601 with:
- Username: elastic
- Password: [value from elasticpassword in .env]

Available metrics include:
- Nginx access and error logs
- HAProxy traffic distribution metrics
- System and container performance metrics

## Troubleshooting

Common troubleshooting steps:
- Verify containers: `docker-compose ps`
- Check logs: `docker-compose logs [service_name]`
- Inspect networks: `docker network inspect [network-name]`

## Data Persistence

Data is persisted using Docker volumes:
- WordPress content
- MariaDB database
- Elasticsearch data
- Kibana configuration
- SSL certificates

## License

MIT

---
Created by: FabFromTheSnow
Last Updated: 2025-04-09 13:42:11 UTC
EOL
```

2. Add the file to the Git repository:
```bash
git add README.md
```

3. Commit the changes:
```bash
git commit -m "Add comprehensive README documentation"
```

4. Push to the remote repository:
```bash
git push origin main
```

If you're pushing to a different branch, replace `main` with your branch name.

The README.md file will now be visible on your repository's GitHub page, providing comprehensive documentation for anyone who visits your project.
