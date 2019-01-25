# Use official Python runtime as parent image
FROM python:2.7-slim

# Set working directory
WORKDIR /app

# Copy contents of current directory into container
COPY . /app

# Install any needed packagees specified in requirements.txt
RUN pip install --trusted-host pypi.python.org -r requirements.txt

# Expose port 80 to the world outside of this container
EXPOSE 80

# Define environment variable
ENV NAME World

# Run app.py when the container launches
CMD ["python", "app.py"]
