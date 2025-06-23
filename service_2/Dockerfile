# Use official Python image
FROM python:3.11-slim

# Set working directory
WORKDIR /app

# Copy source code
COPY app.py .  
COPY pyproject.toml .

# Install Flask
RUN pip install --no-cache-dir flask

RUN apt-get update && apt-get install -y curl

# Expose the port the app runs on
EXPOSE 8002

# Run the Flask app
CMD ["python", "app.py"]

