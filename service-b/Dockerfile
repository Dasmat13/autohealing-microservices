FROM python:3.10-slim
WORKDIR /app

# Install essential tools + dependencies
RUN apt-get update && \
    apt-get install -y curl wget && \
    rm -rf /var/lib/apt/lists/* && \
    pip install flask prometheus-client gunicorn

COPY app.py .
EXPOSE 5000
CMD ["gunicorn", "--bind", "0.0.0.0:5000", "app:app"]