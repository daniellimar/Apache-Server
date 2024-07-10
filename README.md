# Apache Server - Docker Project

This project sets up an Apache web server using Docker. It provides a basic environment to host your web applications.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [License](#license)

## Prerequisites

Before you begin, ensure you have the following installed on your machine:

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Installation

1. **Clone the Repository**

    ```bash
    git clone https://github.com/your-username/apache-docker-project.git
    cd apache-docker-project
    ```

2. **Build the Docker Image**

    ```bash
    docker-compose build
    ```

## Usage

1. **Start the Container**

    ```bash
    docker-compose up -d
    ```

   This command starts the container in detached mode. The Apache server will be running and accessible on port 80.

2. **Stop the Container**

    ```bash
    docker-compose down
    ```

3. **View Logs**

   To view the logs of the running container, use:

    ```bash
    docker-compose logs -f
    ```

## Configuration

1. **Apache Configuration**

   The Apache configuration files are located in the `apache` directory. You can modify the `httpd.conf` file to
   customize the server settings.

    ```bash
    apache/
    └── httpd.conf
    ```

2. **Document Root**

   The default document root for the Apache server is the `html` directory. Place your web application files in this
   directory.

    ```bash
    html/
    └── index.html
    ```

3. **Docker Compose File**

   The `docker-compose.yml` file defines the Docker services. You can modify this file to add more services or change
   the configuration.

    ```yaml
    version: '3'
    services:
      apache:
        image: httpd:latest
        container_name: apache-server
        volumes:
          - ./html:/usr/local/apache2/htdocs/
          - ./apache/httpd.conf:/usr/local/apache2/conf/httpd.conf
        ports:
          - "80:80"
    ```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Feel free to contribute to this project by submitting issues or pull requests. For any questions or suggestions, please
contact [your-email@example.com](mailto:your-email@example.com).