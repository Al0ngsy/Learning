# 2. Dependencies

**Don't rely on implicit existence of system-wide packages.** Declare all dependencies explicitly in a manifest file:

- `requirements.txt` for Python
- `package.json` for Node.js
- `Gemfile` for Ruby

Use a **dependency manager** to handle the installation and versioning of these dependencies.

**Version control** (by version numbers) and **isolation** (using virtual environments like `venv` for Python or containers like Docker) are crucial to ensure consistent app execution across environments.

Example Dockerfile for a Python application:
```Dockerfile
# Use an official Python runtime as a parent image
FROM python:3.10-alpine

# Set the working directory in the container
WORKDIR /app

# Copy the requirements file into the container at /app
COPY requirements.txt /app

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application code into the container
COPY . /app

# Run the application
CMD python app.py
```

Docker commands to build and run the container:
```bash
# Build the Docker image
docker build -t my-python-app .

# Run the Docker container
docker run -d -p 5000:5000 my-python-app
```

## Key points

- Always pin dependency versions to avoid surprises from transitive updates.
- Use lockfiles where available (`pip-tools`, `package-lock.json`, `Pipfile.lock`).
- Prefer containerization for environment consistency in CI/CD pipelines.
