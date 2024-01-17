# Quick-Quiz

Quick-Quiz is a general knowledge quiz application based on Dev James Q Quick's video tutorials.

## Deployment

The application is deployed and accessible at [https://quick-quiz-six.vercel.app/](https://quick-quiz-six.vercel.app/).

## Description

The application uses the 'https://the-trivia-api.com/v2/questions' API to fetch trivia questions. Questions are formatted and presented to the user in an interactive general knowledge quiz format.

## Source Code

The main source code is in the JavaScript file. Here is a breakdown of the relevant code:

```javascript
fetch('https://the-trivia-api.com/v2/questions')
    .then(res => {
        return res.json();
    })
    .then(loadedQuestions => {
        questions = loadedQuestions.map(loadedQuestion => {
            const formattedQuestion = {
                question: loadedQuestion.question.text
            }

            const answerChoices = [...loadedQuestion.incorrectAnswers];
            formattedQuestion.answer = Math.floor(Math.random() * 4) + 1;
            answerChoices.splice(
                formattedQuestion.answer - 1,
                0,
                loadedQuestion.correctAnswer
            );

            answerChoices.forEach((choice, index) => {
                formattedQuestion["choice"+(index+1)] =  choice
            })

            return formattedQuestion;
        });
        startGame();
    })
```
## Usage

1. Access the application at [https://quick-quiz-six.vercel.app/](https://quick-quiz-six.vercel.app/).
2. Enjoy the trivia questions and choose your answers.
3. Check your answers and have fun playing.

Have a great time!
