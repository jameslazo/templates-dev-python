FROM python:3.9-slim

# Uncomment for ENV VARS
# ARG API_KEY
# ENV API_KEY=$ENV_API_KEY

# Create non-root user
RUN useradd -M -s /bin/bash cool-user

# Set the working directory inside the container
WORKDIR /app

# Change ownership of the working directory & switch to user
RUN chown -R cool-user:cool-user .
USER cool-user

# Copy the requirements file into the container
COPY /app .

# Install dependencies
RUN pip install -r requirements.txt

# Expose the port your app runs on
EXPOSE 8080

# Command to run the application
CMD ["python", "app.py"]
