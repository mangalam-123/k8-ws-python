FROM python:3.9-alpine

# Set up a working directory
WORKDIR /app

# Copy requirements.txt
COPY requirements.txt ./

# Create a non-root user 'play'
RUN adduser -D play

# Set ownership of the directory to the 'play' user
RUN chown -R play:play /app

# Switch to the 'play' user
USER play

# Install dependencies as 'play'
RUN pip install --no-cache-dir --user -r requirements.txt

# Copy application files as 'play' user
COPY --chown=play:play . /app

# Expose the application port
EXPOSE 8083

# Run the Python application
CMD ["python", "order_app.py"]

