# One-to-One Chat Application with Spring Boot & WebSocket

A simple, private one-to-one chat application built using Spring Boot, WebSocket (STOMP), and MongoDB for message persistence.

## Features

* Real-time one-to-one messaging using WebSocket and STOMP
* Message persistence in MongoDB
* User-friendly front-end with HTML, CSS, and JavaScript (SockJS & StompJS)
* Docker Compose setup for MongoDB

## Tech Stack

* **Backend:** Java 17, Spring Boot, Spring WebSocket, Spring Data MongoDB
* **Frontend:** HTML, CSS, JavaScript, SockJS, StompJS
* **Database:** MongoDB
* **Build & Packaging:** Maven (with Maven Wrapper)
* **Containerization:** Docker, Docker Compose

## Prerequisites

* Java 17 or higher
* Maven (or use included Maven Wrapper: `./mvnw`)
* Docker & Docker Compose (for MongoDB)

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/shivamshaw23/ChatAppWebSocket.git
cd ChatAppWebSocket/one-to-one-chat-spring-boot-web-socket-main
```

### 2. Configure MongoDB

The project is preconfigured to connect to MongoDB on `localhost:27017`. If you need to change the host/port/database, edit `src/main/resources/application.properties`:

```properties
spring.data.mongodb.host=localhost
spring.data.mongodb.port=27017
spring.data.mongodb.database=chatdb
```

### 3. Start MongoDB with Docker Compose

```bash
docker-compose up -d
```

This will start a MongoDB instance accessible on port 27017.

### 4. Build and Run the Application

Using Maven Wrapper:

```bash
./mvnw clean spring-boot:run
```

Or, if you have Maven installed:

```bash
mvn clean spring-boot:run
```

The application will start on `http://localhost:8088`.

## Usage

1. Open your browser and navigate to `http://localhost:8088`.
2. Enter your username and the recipient's username.
3. Send messages in real-time. Messages are stored in MongoDB and will be loaded when the conversation opens.

## Project Structure

```
one-to-one-chat-spring-boot-web-socket-main/
├── docker-compose.yml        # MongoDB service definition
├── mvnw, mvnw.cmd            # Maven Wrapper scripts
├── pom.xml                   # Maven project file
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/chatapp/
│   │   │       ├── ChatApplication.java      # Main Spring Boot application class
│   │   │       ├── config/
│   │   │       │   └── WebSocketConfig.java  # STOMP over WebSocket configuration
│   │   │       ├── controller/
│   │   │       │   └── ChatController.java   # WebSocket message endpoints
│   │   │       ├── model/
│   │   │       │   └── ChatMessage.java      # Message payload and MongoDB document
│   │   │       ├── repository/
│   │   │       │   └── ChatRepository.java   # MongoDB repository for persistence
│   │   │       └── service/
│   │   │           └── ChatService.java      # Business logic for saving and retrieving messages
│   │   └── resources/
│   │       ├── static/
│   │       │   ├── index.html                # Chat UI
│   │       │   └── js/chat.js                # Front-end WebSocket client logic
│   │       └── application.properties
└── README.md                  # This file
```

## Contributing

Contributions are welcome! Feel free to open issues or submit pull requests for bug fixes, enhancements, or new features.

