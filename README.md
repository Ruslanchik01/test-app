# quiz-cli

## Overview

`quiz-cli` is an interactive command-line quiz game that loads multiple-choice questions from a JSON question bank and runs a scored quiz session in your terminal.

Key features:
- Choose a quiz category and number of questions
- Answer by entering the option number
- Progress bar + final score summary
- Review incorrect answers at the end
- Play-again loop

## Tools / Tech Stack

- Node.js (ES modules; requires Node >= 18 per `test-app/package.json`)
- npm scripts for running/testing
- No external runtime dependencies (uses Node built-in modules like `readline` and `fs/promises`)

## Project Structure

> The runnable app lives under `test-app/`.

- `test-app/index.js` — CLI entrypoint (loads questions, category selection loop)
- `test-app/data/questions.json` — question bank (categories + multiple-choice questions)
- `test-app/src/input.js` — readline-based prompts (select/confirm/press-enter)
- `test-app/src/quiz.js` — quiz engine (shuffle, scoring, progress bar, results)
- `test-app/src/colors.js` — ANSI color helpers

## Prerequisites

- Node.js >= 18

## Setup

```bash
git clone <repo-url>
cd test-app
```

Install (there are currently no external dependencies, but this keeps the standard workflow consistent):

```bash
npm install
```

## Run

```bash
npm start
```

## Testing

```bash
npm test
```

This runs Node's built-in test runner (`node --test`) as defined in `test-app/package.json`.

## Getting Started

1. Start the app:

   ```bash
   npm start
   ```

2. Choose a category.
3. Choose how many questions to answer.
4. Answer each question by entering the option number shown in the prompt.

After the final question, the CLI prints your score and a review list for any incorrect answers.
