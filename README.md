# Docker Training

## The need for Docker

- Docker là gì ?!
- Lí do cần Docker ?!
- Cài đặt Docker như thế nào ?!
- .....

## Chạy ứng dụng bên trong Docker Container

- Không quan trọng ngôn ngữ là gì, một khi chúng ta đã có hiểu biết về Docker, tất cả đều giống nhau.

### Chạy ứng dụng Python bên trong Docker Container

- Trong ví dụ đầu tiên, chúng ta sẽ thử chạy 1 ứng dụng Python đơn giản bên trong Docker Container.
![alt text](image.png)

- Hiện tại tôi muốn gắn thư mục python hiện tại vào thư mục `/app` bên trong Docker Container, và chạy ứng dụng Python này.

- Chúng ta sẽ sử dụng câu lệnh `docker run` sau đó chạy sử dụng cờ `-v` (viết tắt của `--volume`) để gắn thư mục hiện tại vào thư mục `/app` bên trong Docker Container.
- Bên trong docker container, để chúng ta có thể chạy ứng dụng Python, chúng ta cần phải cài đặt môi trường Python trước

- Chúng ta sẽ sử dụng 1 image có sẵn trên Hub đó là `python:3.8-slim` để chạy ứng dụng Python này.

- Giả sử chúng ta không biết gì về Python, làm gì để chúng ta có thể chạy ứng dụng Python này bên trong Docker Container?

``` text
# Developer: Hey there, Captain DevOps! To run this application without Docker, simply execute:
#            python python-app.py
#            I trust that you can take it from here and work your container magic. Smooth sailing!
```

```bash
docker run -v "D:\SeniorProject2025\docker-kube-tranning\docker-tranning\run-application-inside-docker-container\python:/app/" python:3.8-slim python /app/python-app.py
```

- Chúng ta sẽ sử dụng câu lệnh `docker run` để chạy ứng dụng Python này bên trong Docker Container.
- Chúng ta sẽ sử dụng cờ `-v` để gắn thư mục hiện tại vào thư mục `/app` bên trong Docker Container.
- Chúng ta sẽ sử dụng image `python:3.8-slim` để chạy ứng dụng Python này.
- Chúng ta sẽ sử dụng câu lệnh `python /app/python-app.py` để chạy ứng dụng Python này bên trong Docker Container. bên trong Docker Container.

![alt text](image-1.png)
![alt text](image-2.png)

- Bạn cũng có thể đặt tên cho container của mình bằng cách sử dụng cờ `--name` và thêm cờ `--rm` để tự động xóa container khi nó dừng lại.

```bash
docker run --name my-python-app --rm -v "D:\SeniorProject2025\docker-kube-tranning\docker-tranning\run-application-inside-docker-container\python:/app/" python:3.8-slim python /app/python-app.py
```

- Nên đặt tên cho container của bạn để dễ dàng quản lý và theo dõi.

- Xóa image bằng câu lệnh:

```bash
docker rmi python:3.8-slim
docker image rm python:3.8-slim
```

### Chạy ứng dụng Java bên trong Docker Container

- Trong ví dụ tiếp theo, chúng ta sẽ thử chạy 1 ứng dụng Java đơn giản bên trong Docker Container.

![alt text](image-3.png)

- Hướng dẫn:

```text
Developer: Greetings, Captain DevOps! This application is usually executed with the command:
           java -cp JavaApp.jar JavaApp
           However, I have full confidence in your abilities to containerize it and unleash its full potential. Fair winds and following seas!

```

```bash
docker run -v "D:\SeniorProject2025\docker-kube-tranning\docker-tranning\run-application-inside-docker-container\java:/app/" openjdk:11 java -cp /app/JavaApp.jar JavaApp
```

- Kết quả:

![alt text](image-4.png)

- Có thể dùng ChatGPT để convert các câu lệnh để chạy trên Windows sang Linux hoặc ngược lại.

### Chạy ứng dụng Ruby bên trong Docker Container

- Hướng dẫn:

```text
# Developer: Captain DevOps, this Ruby script generates a random inspirational quote and prints it along with an ASCII art border.
#            To run this script, you would typically use the command:
#            ruby script.rb
#            I trust you'll navigate the execution of this script within a Docker container with ease!
```

```bash
docker run -v "D:\SeniorProject2025\docker-kube-tranning\docker-tranning\run-application-inside-docker-container\ruby:/app/" ruby:3.0 ruby /app/script.rb
```

- Kết quả:
![alt text](image-5.png)

### Chạy ứng dụng Golang bên trong Docker Container

- Hướng dẫn:

```text
// Developer: Captain DevOps, this app expects an environment variable named "MESSAGE" to customize the greeting.
//            If "MESSAGE" is not set, it defaults to "Hello, World!".
//            To run the app, navigate to the directory containing main.go and execute: go run main.go
//            I trust you'll handle the environment setup and deployment with ease!


// PS:        Environment variables are key-value pairs that are typically set outside the application, and accessed inside the application.
```

```bash
docker run -e MESSAGE="Hello, Docker!" -v "D:\SeniorProject2025\docker-kube-tranning\docker-tranning\run-application-inside-docker-container\go:/app/" golang:1.20 go run /app/main.go
```

- Giải thích:
- Chúng ta sẽ sử dụng cờ `-e` để thiết lập biến môi trường
- Chúng ta sẽ sử dụng cờ `-v` để gắn thư mục hiện tại vào thư mục `/app` bên trong Docker Container.
- Chúng ta sẽ sử dụng image `golang:1.20` để chạy ứng dụng Go này.
- Chúng ta sẽ sử dụng câu lệnh `go run /app/main.go` để chạy ứng dụng Go này bên trong Docker Container.

- Kết quả:
![alt text](image-6.png)

## Building Docker Images From Dockerfile
