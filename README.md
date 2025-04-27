# Setting up Nginx with Certbot using Docker Compose

Setting up Nginx with Certbot (Let's Encrypt) can be a complex task, especially if you want to use Docker. Many guides on the internet require multiple steps and a good understanding of how the components should work together. This setup is designed to simplify the configuration of Nginx with Certbot using Docker Compose, working right out of the box.

## How It Works

- Copy and Run: Simply copy the provided setup to your server and run docker compose up.
- First Run Setup: On the first run:
  - Certificates will be requested from Let's Encrypt.
  - The certificates will be passed into the Nginx container.
  - Nginx will start without any hassle.
- Automatic Renewal: A separate container with Certbot will automatically renew SSL certificates and restart Nginx as needed.

## Features

- Minimalist Build: The setup consists of just a few files.
- Security Focused: Maximizes the use of internal mechanisms of Certbot and Nginx for improved security in the configuration.

## Steps to Get Started

- Clone this repository to your server: 

```
git clone <repository-url>
cd docker-nginx-certbot
cp docker-compose.yml.example docker-compose.yml
```

Update domain and email
```
DOMAIN: '<your domain>'
```

```
EMAIL: '<your email>'

```

Start the Docker containers: 

```
docker compose up

```

That's it! Your Nginx server with automatic SSL certificate management should now be up and running.
