# Use latest Ubuntu
FROM ubuntu:latest

# Update package list
RUN apt-get update

# Upgrade installed packages
RUN apt-get upgrade -y

# Install python3 and pip3
RUN apt-get install -y python3 python3-pip

# Remove EXTERNALLY-MANAGED if needed to allow pip installs
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED || true

# Install Flask using pip3
RUN pip3 install flask

# Set working directory
WORKDIR /app

# Copy Flask API script to container
COPY ./api.py /app/api.py

# Run the flask server
CMD ["python3", "api.py"]
