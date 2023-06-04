# Set the base image according to the selected device
FROM pytorch/pytorch:latest

# Set the working directory
WORKDIR /app

COPY ./packages-apt.txt .
# Install any additional system packages needed
RUN DEBIAN_FRONTEND=noninteractive apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y \
    build-essential \
    cmake \
    git \
    && rm -rf /var/lib/apt/lists/*
RUN apt-get update && xargs -a packages-apt.txt apt-get install -y


# Copy requirements.txt into the container
COPY ./packages-python3.txt .

# Install any additional Python packages needed
RUN pip install --no-cache-dir -r packages-python3.txt

# Copy the rest of the application code into the container
COPY . .

# Set the entrypoint command
ENTRYPOINT ["/app/docker/entrypoint.sh"]
