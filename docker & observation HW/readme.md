# Redis Flask App in Docker

This project is a **Flask application** instrumented with **Prometheus metrics** and using **Redis** as a key-value store. The application is containerized with Docker and monitored with **Grafana**.

## Features
- Add and retrieve items from Redis
- List all Redis items
- Instrumented endpoints with Prometheus metrics
- Tracks cache hits and cache misses
- `/metrics` endpoint for Prometheus scraping

## API Endpoints
| Method | Endpoint         | Description                        |
|--------|-----------------|------------------------------------|
| GET    | `/`             | Hello message                      |
| POST   | `/items`        | Add an item to Redis               |
| GET    | `/items/<key>`  | Get a specific item by key         |
| GET    | `/items`        | List all items                     |
| GET    | `/metrics`      | Prometheus metrics                 |

## Metrics
- **Cache hits** tracked per key (`redis_app_cache_hit`)
- **Cache misses** (`redis_app_cache_miss`)
- HTTP request counts and durations

## Grafana Dashboard
Here is an example of monitoring cache hits and misses in Grafana:
<img width="1591" height="685" alt="image" src="https://github.com/user-attachments/assets/c588594d-06d5-4021-8564-d3c2ce3f0231" />



## How to Run
```bash
# Install dependencies
pip install -r requirements.txt

# Run Flask app
python app.py
