## Weatherstack Redis Poller

Simple Python service that calls the Weatherstack API, stores weather data in Redis, and serves cached results over HTTP.

## Prerequisites

- Python 3
- Redis running locally or in Docker
- Weatherstack API key

## Setup

1. Clone this repo:
```bash
   - git clone https://github.com/Bharathi-vbr/weatherstack-redis-poller
   - cd weatherstack-redis-poller
   ```

2. (Optional) Create virtual environment:
```bash
   - python -m venv venv
   - Windows: venv\Scripts\activate
   - macOS/Linux: source venv/bin/activate
```
3. Install dependencies directly with pip (example):
```bash
   - pip install redis
   - pip install requests
   - pip install flask  # or fastapi, depending on what you use
 ```

4. Set environment variables (or .env):
  ```bash
   - WEATHERSTACK_API_KEY=<your_key>
   - REDIS_URL=redis://localhost:6379
   - PORT=8000
 ```

## Run
- Start Redis.
- Run the script:
  - python3 main.py
- The script will:
  - Call the Weatherstack API.
  - Store weather data in Redis.

## Usage

- Example:
  - GET /weather?city=London
- The service:
  - Checks Redis for cached data.
  - If cache hit and fresh, returns it.
  - Otherwise calls Weatherstack, stores result in Redis, and returns it.
