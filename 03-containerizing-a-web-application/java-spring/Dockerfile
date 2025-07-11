## 1. Which base image do you want to use?

## 2. Set the working directory.

## 3. Copy the application's project files into the working directory.

## 4. Document and inform the developer that the application will use the container port: 8080.

## 5. Define the command to run when the container starts.

##################

### Cách 1

# ## 1. Which base image do you want to use?

# FROM maven:3.8-openjdk-17-slim

# ## 2. Set the working directory.

# WORKDIR /app

# ## 3. Copy the application's project files into the working directory.

# COPY springboot-demo  /app

# # COPY springboot-demo  .

# ## 4. Document and inform the developer that the application will use the container port: 8080.

# EXPOSE 8080

# ## 5. Define the command to run when the container starts.

# CMD ["mvn", "clean", "spring-boot:run"]


################### 

### Cách 2

## 1. Which base image do you want to use?

FROM maven:3.8-openjdk-17-slim

## 2. Set the working directory.

WORKDIR /app

## 3. Copy the application's project files into the working directory.

COPY springboot-demo  /app

# COPY springboot-demo  .

### Cách 2

RUN mvn install

## 4. Document and inform the developer that the application will use the container port: 8080.

EXPOSE 8080

## 5. Define the command to run when the container starts.

CMD ["mvn", "spring-boot:run"]