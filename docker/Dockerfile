# Set the base image according to the selected device
FROM pytorch/pytorch:latest

# Set the working directory
WORKDIR /app

# Install any additional system packages needed
RUN apt-get update && apt-get install -y \
    build-essential \
    cmake \
    git \
    && rm -rf /var/lib/apt/lists/*

# Copy requirements.txt into the container
COPY ./packages-python3.txt .

# Install any additional Python packages needed
RUN pip install --no-cache-dir -r packages-python3.txt

# Copy the rest of the application code into the container
COPY . .

# Set the entrypoint command
ENTRYPOINT ["/app/docker/entrypoint.sh"]
