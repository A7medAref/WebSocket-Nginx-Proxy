# WebSocket-Nginx-Proxy

This repository contains a Docker-based setup for demonstrating an Nginx configuration that acts as a Layer 7 Load Balancer and a Layer 4 Proxy to proxy packets directly without new handshaking. The setup includes a simple Node.js application that utilizes Socket.IO for real-time communication.

## Architecture Overview

The configuration demonstrates how to use Nginx at two different layers:

- **Layer 7 (Application layer) Load Balancer**: Handles HTTPS traffic and routes WebSocket requests.
- **Layer 4 (Transport Layer) Proxy**: Forwards TCP traffic transparently to the Node.js backend.

This architecture helps in understanding how Nginx can be configured to handle traffic at different OSI model layers, providing flexibility in managing both HTTP and WebSocket traffic.

### Components

1. **Node.js Application (Socket.IO)**: A basic real-time WebSocket server using Socket.IO.
2. **Nginx L7 Load Balancer**: Configured to handle HTTPS and WebSocket upgrade requests.
3. **Nginx L4 Proxy**: Set up to forward traffic to the Node.js application. Simple routing with minimum overhead.

## Setup and Configuration

### Prerequisites

- Docker
- Docker Compose
- Node.js

### Configuration Files

- `Dockerfile`: Dockerfile for building the Node.js Socket.IO application.
- `nginx-l4.conf`: Configuration for Nginx as a Layer 4 TCP proxy.
- `nginx-l7.conf`: Configuration for Nginx as a Layer 7 HTTP/HTTPS load balancer.
- `docker-compose.yml`: Docker Compose file to orchestrate the deployment of the Node.js app and both Nginx instances.

## Usage

To run:

1. ```bash
   docker compose up --build
   ```
