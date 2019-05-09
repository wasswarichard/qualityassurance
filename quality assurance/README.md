[![Build Status](https://travis-ci.org/Ogwang/StackOverflowLite.svg?branch=master)](https://travis-ci.org/Ogwang/StackOverflowLite)
[![Coverage Status](https://coveralls.io/repos/github/Ogwang/StackOverflowLite/badge.svg?branch=master)](https://coveralls.io/github/Ogwang/StackOverflowLite?branch=master)
[![Maintainability](https://api.codeclimate.com/v1/badges/cd7c0d1d39a95c0efe70/maintainability)](https://codeclimate.com/github/Ogwang/StackOverflowLite/maintainability)

# StackOverflowLite# 
StackOverflowLite is a platform where people can ask questions and provide answers.


## Project Overview
StackOverflow-lite is a platform where people can ask questions and provide answers.

## Required Features
    - Users can create an account and log in.
    - Users can post questions.
    - Users can delete the questions they post
    - Users can post answers
    - Users can view the answers
    - Users can accept an answer out of all the answers to his/her queston as they preferred answer
    - Users can upvote or downvote an answer.
    - Users can comment on an answer.
    - Users can fetch all questions he/she has ever asked on the platform
    - Users can search for questions on the platform
    - Users can view questions with the most answers.

## Installation

```
  
    $ git clone https://github.com/Ogwang/StackOverflowLite.git
    $ cd stackoverflow-lite
    $ virtualenv venv
    $ . venv/bin/activate
    $ pip install -r requirements.txt   
```
## Running the application
```
    $ export DATABASE_URL="Your DATABASE_URL"
``` 
or open .env file and copy your postgres database url
```
    #.env file
    DATABASE_URL=postgres://username:password@hostname/databasename
    
    $ python manage.py runserver
```

## Testing
``` 
    $ pytest --cov=app
```

## Endpoints

## Users Endpoints

Method | Endpoint | Functionality
--- | --- | ---
POST | `/api/v1/auth/signup` | Add a user
GET | `/api/v1/auth/users` | Lists all users
GET | `/api/v1/auth/users/{user_id}` | Retrieve a user
POST | `/api/v1/auth/login` | Login a user

## Questions Endpoints

Method | Endpoint | Functionality
--- | --- | ---
POST | `/api/v1/questions` | Add a question
GET | `/api/v1/questions` | Lists all questions
GET | `/api/v1/questions/?q={search_string}` | Search a questions
GET | `/api/v1/questions/{question_id}` | Retrieve a question
PUT | `/api/v1/questions/{question_id}` | Edit a question of a logged in user
DELETE | `/api/v1/questions/{question_id}` | Delete a request of a logged in user

## Answers Endpoints

Method | Endpoint | Functionality
--- | --- | ---
POST | `/api/v1/questions/{question_id}/answers` | Add an answer
GET | `/api/v1/questions/answers` | Lists all answers
GET | `/api/v1/questions/answers/{answerID}` | Retrieve an answer
PUT | `/api/v1/questions/{question_id}/answer/{answerID}` | Edit an answer
DELETE | `/api/v1/questions/{question_id}/answer/{answerID}` | Delete an answer
POST | `/api/v1/questions/answers/vote/{answer_id}` | Upvote/DownVote an answer
POST | `/api/v1/questions/answers/comment/{answer_id}` | Comment on an answer

## Author
Denis Ogwang.

