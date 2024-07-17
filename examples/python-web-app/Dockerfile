# Use the official Ubuntu image as a parent image
FROM ubuntu:latest

# Set the working directory in the container
WORKDIR /app

# Copy the requirements file and the devops directory to the container
COPY requirements.txt /app/
COPY devops /app/devops/

# Update package lists and install Python and pip
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    pip3 install -r /app/requirements.txt

# Set the working directory to the devops directory
WORKDIR /app/devops

# Define the command to run the application
ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]
