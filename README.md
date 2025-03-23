# Prometheus Setup for Flask Application

## Using requirements.txt file : 
```sh
pip install -r requirements.txt
pip freeze
docker run -d -p 9090:9090 -v /path/to/prometheus.yml:/etc/prometheus/prometheus.yml prom/prometheus:v2.41.0

```
## Using Dockerfile : 
```sh
docker build -t my-prometheus .
docker run -d -p 9090:9090 my-prometheus   #on http://localhost:9090

```
## Directly pull the Prometheus image from the Docker registry : 
```sh
docker pull prom/prometheus:v2.41.0
# Run Prometheus with your custom configuration
docker run -d -p 9090:9090 -v /path/to/your/prometheus.yml:/etc/prometheus/prometheus.yml prom/prometheus:v2.41.0
# (-v /path/to/your/prometheus.yml:/etc/prometheus/prometheus.yml: Mounts your custom prometheus.yml from your local system into the container.)
```
