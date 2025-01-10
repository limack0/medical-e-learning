# medical-e-learning

As a low level programmer, the objective is to create a kind of social network for medical student based on React expo django restAPI and postgresql

Below is class diagram shows the relationships between the main entities (models) in the system.
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
