FROM python:3.10 

# Set working directory
WORKDIR /app

# Install system dependencies required for thriftpy
RUN apt update && apt install -y \
    python3-dev \
    build-essential \
    libssl-dev \
    libffi-dev \
    libevent-dev \
    gcc \
    libsnappy-dev \
    liblz4-dev \
    libzstd-dev \
    && rm -rf /var/lib/apt/lists/*  # Clean up to reduce image size

# Upgrade pip, setuptools, and install Cython before requirements
RUN pip install --upgrade pip setuptools wheel Cython

# Copy the necessary files into the container  
COPY ./main.py /app/main.py  
COPY ./requirements.txt /app/requirements.txt

RUN pip install --no-cache-dir -r requirements.txt

# Run the log processor
CMD ["python", "/app/main.py"]
