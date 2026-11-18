# Python Dockerfile

```dockerfile
FROM python:3.12  ## 	Downloads Python 3.12 base image.

WORKDIR /app      ## sets the working directory inside the container.

COPY requirements.txt .  ## Copies the requirements file into the container. ## Stores all Python dependencies required by the application.

RUN pip install -r requirements.txt  ## Installs all Python dependencies.

COPY . .      ## Copy code into the container.

EXPOSE 5000   ## Expose user port 5000.

CMD ["python", "app.py"]    ## Starts the Python application.
```

---

# Node.js Dockerfile

```dockerfile
FROM node:20

WORKDIR /app

COPY package*.json ./   ## required Node.js dependencies and stores the exact dependency versions.

RUN npm install

RUN npm run test

COPY . .

EXPOSE 8000

CMD ["node", "app.js"]
```
