FROM python:3.10-slim
WORKDIR /app
RUN apt-get update && \
    apt-get install -y curl && \
    rm -rf /var/lib/apt/lists/*
RUN pip install flask prometheus-client gunicorn
COPY app.py .
EXPOSE 5000
CMD ["gunicorn", "--bind", "0.0.0.0:5000", "--workers=2", "app:app"]