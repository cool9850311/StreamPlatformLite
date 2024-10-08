# StreamPlatformLite
Stream Platform Lite is a platform that allows any streamer to easily create their own live streaming platform, making their content and revenue not entirely dependent on major streaming platforms.

## Usage

### Prerequisites
- Docker
- Docker Compose

### Setup

1. Clone the repositories:
    ```sh
    git clone https://github.com/cool9850311/StreamPlatformLite.git
    git clone https://github.com/cool9850311/StreamPlatformLite-Frontend.git
    git clone https://github.com/cool9850311/StreamPlatformLite-Backend.git
    ```

2. Navigate to the project directory:
    ```sh
    cd StreamPlatformLite
    ```

3. Copy the example configuration files:
    ```sh
    cp docker-compose-example.yml docker-compose.yml
    cp nginx.conf.example nginx.conf
    ```

4. Update the environment variables in `docker-compose.yml` and `nginx.conf` as needed. (See [Configuration - docker-compose](https://github.com/cool9850311/StreamPlatformLite/wiki/Configuration-%E2%80%90-docker-compose))

5. replace cert & key file in certs folder with your own.

### Running the Application

1. Start the services using Docker Compose:
    ```sh
    # docker-compose or docker compose based on your docker compose version
    docker-compose up -d --build
    ```

### Stopping the Application

1. To stop the services, run:
    ```sh
    # docker-compose or docker compose based on your docker compose version
    docker-compose down
    ```

For more detailed information, refer to the individual repository links provided below.

## Frontend
[link](https://github.com/cool9850311/StreamPlatformLite-Frontend)

## Backend
[link](https://github.com/cool9850311/StreamPlatformLite-Backend)
