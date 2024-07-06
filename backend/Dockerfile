# Use an official Python runtime as a parent image
# FROM python:3.9-slim
FROM python:3.10

RUN set -xe

# Set environment variables
# ENV POETRY_VERSION=1.1.11 \
#     POETRY_VIRTUALENVS_CREATE=false \
#     PYTHONDONTWRITEBYTECODE=1 \
#     PYTHONUNBUFFERED=1

# Install system dependencies
# RUN apt-get update && \
#     apt-get install --no-install-recommends -y \
#     curl \
#     build-essential \
#     && rm -rf /var/lib/apt/lists/*

# Install Poetry
RUN curl -sSL https://install.python-poetry.org | python3 - --git https://github.com/python-poetry/poetry.git@master

ENV PATH="/root/.local/bin:$PATH"

RUN poetry --version
# RUN poetry new foobar

# Set up the working directory
WORKDIR /app

# Copy and install dependencies
# COPY pyproject.toml poetry.lock ./
COPY . /app

# RUN chmod +x ./prestart.sh
RUN poetry install

# RUN poetry run bash ./prestart.sh


EXPOSE 8002

# Copy the rest of the application code

# Start the application

CMD ["bash", "-c", "poetry run bash ./prestart.sh && poetry run uvicorn app.main:app --reload --host 0.0.0.0"]