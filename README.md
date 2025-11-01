# StreamPlatformLite
Stream Platform Lite is a platform that allows any streamer to easily create their own live streaming platform, making their content and revenue not entirely dependent on major streaming platforms.

## Deployment Options

StreamPlatformLite supports two deployment methods. **Caddy is recommended** for its simplicity and automatic HTTPS.

### Option 1: Caddy (Recommended - Automatic HTTPS)

**Advantages:**
- Automatic SSL certificate from Let's Encrypt
- Auto-renewal (no manual maintenance)
- Simpler configuration
- Better security (backend not directly exposed)
- HTTP/2 and HTTP/3 support out of the box

**Prerequisites:**
- Docker & Docker Compose
- Domain name with DNS A record pointing to your server
- Ports 80, 443, and 1935 open in firewall

**Setup:**

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

3. Copy the Caddy configuration files:
    ```sh
    cp docker-compose-caddy.yml docker-compose.yml
    cp Caddyfile.example Caddyfile
    ```

4. Edit `Caddyfile` and replace `example.com` with your actual domain name.

5. Update the environment variables in `docker-compose.yml`:
    - Replace `example.com` with your domain in `DOMAIN` and `FRONTEND_DOMAIN`
    - Update other environment variables as needed
    - (See [Configuration - docker-compose](https://github.com/cool9850311/StreamPlatformLite/wiki/Configuration-%E2%80%90-docker-compose))

6. Start the services:
    ```sh
    docker-compose up -d --build
    ```

7. Wait 1-2 minutes for Caddy to obtain SSL certificates automatically.

**Notes:**
- Certificates are stored in Docker volumes and renewed automatically
- No manual certificate management needed
- Access your site at `https://yourdomain.com`

### Option 2: Nginx (Traditional Method)

**Use this if:**
- You prefer manual certificate management
- You already have SSL certificates
- You need specific Nginx features

**Setup:**

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

5. Replace cert & key files in `certs` folder with your own SSL certificates.

6. Start the services using Docker Compose:
    ```sh
    docker-compose up -d --build
    ```

### Stopping the Application

To stop the services (works for both Caddy and Nginx):
```sh
docker-compose down
```

For more detailed information, refer to the individual repository links provided below.

## Frontend
[link](https://github.com/cool9850311/StreamPlatformLite-Frontend)

## Backend
[link](https://github.com/cool9850311/StreamPlatformLite-Backend)
