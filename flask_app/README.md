# Flask App — AWS ECS Deployment

A minimal Flask web application built for learning containerization and deployment to **AWS ECS (Elastic Container Service)**.

## Features

- Responsive landing page with modern glassmorphism UI
- `/health` endpoint for ECS load balancer health checks
- Two Dockerfiles — simple and multistage (distroless)

## Project Structure

```
flask-app-ecs/
├── app.py                 # Flask app with routes
├── run.py                 # Entry point (host 0.0.0.0, port 80)
├── requirements.txt       # Python dependencies
├── templates/
│   └── index.html         # Landing page
├── Dockerfile             # Simple single-stage build
└── Dockerfile-multi       # Multistage build with distroless