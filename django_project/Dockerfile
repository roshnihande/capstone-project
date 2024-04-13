# Use an existing Python image as the base
FROM python:3.10

# Set the working directory inside the Docker container
WORKDIR /usr/src/app

# Copy requirements.txt and install dependencies
COPY project/requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

# Install Gunicorn
RUN pip install gunicorn

# Copy application code
COPY project/django_app/ ./django_app
COPY project/project/ ./project


# Expose port
EXPOSE 8000

# Run Django server
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "project.wsgi:application"]
