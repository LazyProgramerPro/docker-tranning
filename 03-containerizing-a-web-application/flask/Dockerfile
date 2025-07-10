## 1. Which base image do you want to use?

FROM python:3.9-slim
## 2. Set the working directory
WORKDIR /app/

## 3. Copy the project files into the working directory.
COPY . . 

## 4. Install the dependencies
RUN pip install -r flask-app-demo/requirements.txt

## 5. Document and inform the developer that the application will use PORT 5000 of the container.
EXPOSE 5000

## 6. Define the command to run when the container starts.

CMD ["python", "flask-app-demo/app.py"]