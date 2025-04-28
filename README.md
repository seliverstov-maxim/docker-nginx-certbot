# Setting up Nginx with Certbot using Docker Compose

Setting up Nginx with Certbot (Let's Encrypt) can be a complex task, especially if you want to use Docker. Many guides on the internet require multiple steps and a good understanding of how the components should work together. This setup is designed to simplify the configuration of Nginx with Certbot using Docker Compose, working right out of the box.

## How It Works

- **Copy and Run**: Simply copy the provided setup to your server and run docker compose up.
- **First Run Setup**: On the first run:
  - Certificates will be requested from Let's Encrypt.
  - The certificates will be passed into the Nginx container.
  - Nginx will start without any hassle.
- **Automatic Renewal**: A separate container with Certbot will automatically renew SSL certificates and restart Nginx as needed.

## Features

- **Minimalist Build**: The setup consists of just a few files.
- **Security Focused**: Maximizes the use of internal mechanisms of Certbot and Nginx for improved security in the configuration (no hard to undestand sh files which need to be verified).

## Steps to Get Started

- Clone this repository to your server: 

```
git clone git@github.com:seliverstov-maxim/docker-nginx-certbot.git
cd docker-nginx-certbot
cp .env.example .env
```

Update domain and email in docker-compose.yml
```
DOMAIN='example.com'
```

```
EMAIL='test@example.com'
```

Start the Docker containers: 

- load domain and email from .env ENVS 
- run docker compose


```
source .env
docker compose up -d

```

That's it! Your Nginx server with automatic SSL certificate management should now be up and running.
