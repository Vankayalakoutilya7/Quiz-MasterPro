Quiz Application Backend (Spring Boot)

A secure and modular backend for quiz applications built with Java Spring Boot, following the MVC (Model-View-Controller) architecture. This project includes authentication, authorization, and quiz management functionalities, making it a great foundation for developing full-stack quiz platforms.

🚀 Features

✔ User Authentication & Authorization
Secure login and role-based access control implemented using JWT.

✔ Quiz Management
Create, update, fetch, and delete quizzes with RESTful APIs.

✔ Question & Options Handling
Add questions and multiple options associated with each quiz.

✔ MVC Architecture
Clean separation of Model, Controller, and Service layers for scalability and maintainability.

🛠️ Tech Stack
| Technology            | Purpose                              |
| --------------------- | ------------------------------------ |
| Spring Boot           | Backend framework                    |
| Spring Security       | Securing APIs with role-based access |
| JWT (JSON Web Token)  | Authentication & authorization       |
| MySQL (or any SQL DB) | Persistent data storage              |
| Maven                 | Dependency & project management      |

⚙️ Installation & Setup

1️⃣ Configure Database Connection
Update src/main/resources/application.properties:

spring.datasource.url=jdbc:mysql://localhost:3306/quizdb
spring.datasource.username=root
spring.datasource.password=your_password
spring.jpa.hibernate.ddl-auto=update

2️⃣ Build & Run the Application

mvn clean install
mvn spring-boot:run


➡ Server will run on:

http://localhost:9000/

📌 API Documentation
🔑 Authentication
➤ Register User
POST {{BASE_URL}}auth/addNewUser


Request Body:

{
  "name": "Devansh",
  "email": "devansh@gmail.com",
  "password": "1234",
  "contact": "7015845944"
}

👤 User Profile
➤ Get Profile
GET {{BASE_URL}}api/profile

📝 Quizzes
➤ Add Quiz
POST {{BASE_URL}}api/Quizzes


Request Body:

{
  "title": "Science Quiz",
  "description": "Test your science knowledge",
  "timeLimit": "00:30:00"
}

➤ Get All Quizzes
GET {{BASE_URL}}api/Quizzes

❓ Questions
➤ Add Question
POST {{BASE_URL}}api/Question


Request Body:

{
  "questionText": "Who discovered gravity?",
  "questionType": "Multiple Choice",
  "quiz": {
    "quizID": 1
  }
}

🔘 Options
➤ Add Option
POST {{BASE_URL}}api/options


Request Body:

{
  "optionText": "Isaac Newton",
  "isCorrect": true,
  "question": {
    "questionID": 4
  }
}

🧑‍🎓 User Attempts
➤ Create Attempt
POST {{BASE_URL}}api/UserAttempt


Request Body:

{
  "quiz": { "quizID": 1 },
  "startTime": "2024-01-23T12:34:56",
  "score": 0
}

🗒 User Responses
➤ Add Response
POST {{BASE_URL}}api/response
