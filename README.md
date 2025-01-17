# Apprendere: Spaced Repetition

## Engineering Team

1. [Erin Dustin](https://github.com/erincdustin)
2. [Lucas Vocos](https://github.com/lucasvocos)

## Overview

Apprendere is an app which helps users learn Italian using “spaced repetition” to help memorize words in a foreign language.

This app maintains a list of Italian words in a database that also includes records of a user’s total score, each word’s correct and incorrect count, and it’s current place in memory.

![Flashcard List](/src/images/flashcard-list.JPG "List of user flashcards")

When the front end sends a guess, our backend server utilizes an algorithm to determine if the guess was correct or incorrect. As words are guessed correctly or incorrectly, those numbers increase accordingly and the words move up or down the list.

![Flashcard Guess](/src/images/flashcard-guess.JPG "User sees success rate of guessing current word and is prompted for guess")

![Flashcard Response](/src/images/flashcard-response.JPG "App evaluates user answer and proceeds to next card")

When the frontend requests the words again, the server responds with an updated list. Therefore, the user spends more time working on the words that they are having trouble with rather than the words they seem to already know.

## Live App

https://apprendere.lucasvocos.now.sh

## Setup

To setup the application

1. Fork and clone the project to your machine
2. `npm install`. This will also install the application *Cypress.io* for running browser integration tests

The project expects you have the Spaced repetition API project setup and running on http://localhost:8000.

Find instructions to setup the API here https://github.com/Thinkful-Ed/spaced-repetition-api.

## Running project

This is a `create-react-app` project so `npm start` will start the project in development mode with hot reloading by default.

## Running the tests

This project uses [Cypress IO](https://docs.cypress.io) for integration testing using the Chrome browser.

Cypress has the following expectations:

- You have cypress installed (this is a devDependency of the project)
- You have your application running at http://localhost:3000.
  - You can change the address of this expectation in the `./cypress.json` file.
- Your `./src/config.js` is using http://localhost:8000/api as the `API_ENDPOINT`

To start the tests run the command:

```bash
npm run cypress:open
```

On the first run of this command, the cypress application will verify its install. Any other runs after this, the verification will be skipped.

The command will open up the Cypress application which reads tests from the `./cypress/integration/` directory. You can then run individual tests by clicking on the file names or run all tests by clicking the "run all tests" button in the cypress GUI.

Tests will assert against your running localhost client application.

You can also start all of the tests in the command line only (not using the GUI) by running the command:

```bash
npm run cypress:run
```

This will save video recordings of the test runs in the directory `./cypress/videos/`.
