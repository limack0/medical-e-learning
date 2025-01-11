# medical-e-learning

As a low level programmer, the objective is to create a kind of social network for medical student based on React expo django restAPI and postgresql

1. Project Overview

The e-learning platform will have the following features:

    User Roles: Students, Trainers, and Admins.

    Account Creation: Users can register based on their level in medicine or pharmacy.

    Q&A Forum: Users can ask questions, add comments, and discuss subjects.

    File Sharing: Users can upload and share files (e.g., PDFs, images).

    Quizzes: Trainers can create quizzes, and students can take them.

    Classroom Sessions: Trainers can create classroom sessions, and students can subscribe to them.

    Authentication & Authorization: Secure access to resources based on user roles.

2.  Tech Stack

    Frontend: React (with Expo for mobile compatibility).

    Backend: Django REST Framework (DRF) for APIs.

    Database: PostgreSQL for data storage.

    Authentication: JWT (JSON Web Tokens) or Django's built-in authentication.

    File Storage: Django's FileField or cloud storage (e.g., AWS S3, Firebase Storage).

    Real-time Features: Use WebSockets (e.g., Django Channels) for live discussions or notifications.

3.  Frontend (React with Expo)
    Pages

        Home Page: Overview of the platform.

        Login/Signup: Authentication pages.

        Dashboard: User-specific dashboard (e.g., questions, quizzes, classrooms).

        Q&A Forum: List of questions and comments.

        Quiz Page: Take quizzes.

        Classroom Page: View and subscribe to classrooms.

        Profile Page: User profile and settings.

Components

    Navbar: Navigation bar.

    QuestionCard: Display a question with comments.

    QuizCard: Display a quiz.

    ClassroomCard: Display a classroom session.

    FileUploader: Component for file uploads.

State Management

    Use React Context API or Redux for state management (e.g., user authentication, quiz scores).

API Integration

    Use axios or fetch to interact with the Django REST API.

4. Backend (Django REST API)

Below is class diagram shows the relationships between the main entities (models) in the system. (refer to ClassDiagram.drawio)
Entities

    User:

        Attributes: id, username, email, password, role, level, specialization

        Relationships: Associated with Question, Comment, Quiz, Classroom, Subscription.

    Question:

        Attributes: id, title, content, created_at

        Relationships: Associated with User (asker) and Comment.

    Comment:

        Attributes: id, content, created_at

        Relationships: Associated with User (commenter) and Question.

    Quiz:

        Attributes: id, title, description, created_at

        Relationships: Associated with User (trainer) and QuizQuestion.

    QuizQuestion:

        Attributes: id, question_text, correct_answer

        Relationships: Associated with Quiz.

    Classroom:

        Attributes: id, title, description, start_time, end_time

        Relationships: Associated with User (trainer) and Subscription.

    Subscription:

        Attributes: id, subscribed_at

        Relationships: Associated with User (student) and Classroom.

    File:

        Attributes: id, file, uploaded_at

        Relationships: Associated with User.

The use case diagram shows the interactions between users (actors) and the system.(refer to UseCaseDiagram.drawio)

ctors

    Student:

        Can ask questions, comment on questions, take quizzes, subscribe to classrooms, and upload files.

    Trainer:

        Can create quizzes, create classroom sessions, answer questions, and upload files.

    Admin:

        Can manage users, questions, quizzes, classrooms, and files.
