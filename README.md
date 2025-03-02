# Simple Node.js Application

This is a basic Node.js application using Express.js framework.

## Prerequisites

- Node.js installed on your machine
- PM2 installed globally (`npm install -g pm2`) on EC2 instance
- Git installed on EC2 instance

## Installation

1. Install dependencies:
```bash
npm install
```

## Running the Application

Start the server:
```bash
npm start
```

The server will start running at http://localhost:3000

## Endpoints

- GET `/`: Returns "Hello World!"

## Deployment Setup

### EC2 Setup Requirements

1. Install Node.js, Git, and PM2 on your EC2 instance
2. Clone this repository to your EC2 instance
3. Set up SSH key-based authentication

### GitHub Actions Setup

The following secrets need to be added to your GitHub repository:

- `EC2_SSH_PRIVATE_KEY`: Your EC2 instance's SSH private key
- `EC2_HOST`: Your EC2 instance's public IP or DNS
- `EC2_USER`: SSH user (usually 'ec2-user' or 'ubuntu')

### Deployment Process

The application automatically deploys to EC2 when changes are pushed to the main branch. The deployment:

1. SSHs into the EC2 instance
2. Pulls the latest changes
3. Installs dependencies
4. Restarts the application using PM2 
do something