## Base Image

## Work Directory

## Install requirements

## Copy source code

## Expose container port

## Execute Application

FROM python:3.8-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY . .

EXPOSE 5001

CMD ["python", "app.py"]