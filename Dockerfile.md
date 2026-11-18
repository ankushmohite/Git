# Use Python base image
FROM python:3.12

# Set working directory
WORKDIR /app

# Copy requirements file
COPY requirements.txt .

# Install dependencies
RUN pip install -r requirements.txt

# Copy application files
COPY . .

# Expose application port
EXPOSE 5000

# Start Python application
CMD ["python", "app.py"]

FROM node:20
WORKDIR app
COPY . .
RUN npm install
RUN npm run test
EXPOSE 8000
CMD ["node","app.js"]
