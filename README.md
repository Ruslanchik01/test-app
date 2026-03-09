# Quiz CLI

## Project Description

`quiz-cli` is an interactive command-line quiz game that loads multiple-choice questions from a JSON question bank and runs a scored quiz session in your terminal.

## Key Features

- Choose a quiz category and number of questions
- Answer by entering the option number
- Progress indicator during the quiz
- Final score summary
- Review incorrect answers at the end
- Play-again loop

## Project Structure

> The runnable app lives under `test-app/`.

- `test-app/index.js` — CLI entrypoint (loads questions and runs the main loop)
- `test-app/package.json` — npm scripts and Node engine requirement
- `test-app/data/questions.json` — question bank (categories + questions)
- `test-app/src/input.js` — readline-based prompts (select/confirm/press-enter)
- `test-app/src/quiz.js` — quiz engine (shuffle, scoring, progress bar, results)
- `test-app/src/colors.js` — ANSI color helpers

## Prerequisites

- Node.js **>= 18** (required by `test-app/package.json`)
- npm (bundled with Node.js)

## Setup Instructions

Clone the repository and install dependencies (there are currently no external runtime dependencies, but `npm install` keeps the workflow consistent):

```bash
git clone <repo-url>
cd <cloned-repo>
cd test-app
npm install
```

## How to Run

From the `test-app/` directory:

```bash
npm start
```

Equivalent:

```bash
node index.js
```

## Usage

1. Start the quiz.
2. Choose a category.
3. Choose how many questions to answer (all, 3, or 5 when available).
4. For each question, enter the number for the option you want.
5. Review your results at the end and choose whether to play again.

## Adding / Editing Questions

Questions are stored in:

- `test-app/data/questions.json`

### Schema

```json
{
  "categories": {
    "<categoryId>": {
      "name": "<Display Name>",
      "questions": [
        {
          "question": "<Question text>",
          "options": ["<Option 1>", "<Option 2>", "<Option 3>", "<Option 4>"],
          "answer": 0,
          "explanation": "<Optional explanation>"
        }
      ]
    }
  }
}
```

### Notes

- `categoryId` is the key under `categories` (for example: `javascript`, `nodejs`).
- `answer` is a **zero-based index** into the `options` array.
- `explanation` is optional; when present it is shown after answering.

## Scripts

Run these from the `test-app/` directory:

- `npm start` — run the CLI (`node index.js`)
- `npm test` — run Node’s built-in test runner (`node --test`)

## License

MIT (see `test-app/package.json`).
