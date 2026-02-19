# VgEliteaDemo — Quiz CLI

## Project description
VgEliteaDemo contains a small interactive command-line quiz application (test-app) written for Node.js using modern JavaScript (ES Modules). It demonstrates a simple, extensible quiz engine that reads question data from JSON and provides a terminal-based interactive experience including category selection, progress display, scoring, and review of incorrect answers.

This repo is designed as a learning/demo project to show:
- ES Modules (import/export)
- Async/await and Promises
- File I/O (reading JSON)
- Basic CLI input handling (readline)
- Class-based design and small utilities (colors, input helpers)
- Array methods and small algorithms (shuffle / Fisher–Yates)

## Repository layout
VgEliteaDemo/
- README.md (this file)
- test-app/
  - data/
    - questions.json — All quiz categories and questions
  - index.js — Entry point and main application loop
  - package.json — Project metadata (type: module)
  - src/
    - colors.js — Small ANSI color helpers
    - input.js — readline-based input helpers (prompt, select, confirm)
    - quiz.js — Quiz class implementing game logic

## Key features
- Multiple categories (JavaScript, Node.js, General Programming) loaded from JSON
- Category selection and choice of number of questions
- Randomized question order (Fisher–Yates shuffle)
- Per-question selection UI with input validation
- Visual progress bar and percentage progress
- Scoring with final percentage and friendly performance messages
- Review of incorrect questions with your answer vs correct answer
- Minimal dependencies — uses only Node.js built-ins (fs/promises, readline, path, url)
- Simple, modular codebase easy to extend (add new categories/questions, change UI, etc.)

## Setup instructions
Prerequisites:
- Node.js 18+ (package.json sets "engines": ">=18.0.0")
  - Verify: node -v

Steps:
1. Clone or copy the repository and change to the test-app directory:
   - cd VgEliteaDemo/test-app
2. (Optional) Install dependencies — this project uses only Node built-ins, so `npm install` is not required. However, if you plan to add dependencies, run:
   - npm install

Notes:
- The project uses ES modules. package.json includes "type": "module", so run with `node index.js` or `npm start` (which runs node index.js).
- The index.js script includes a Unix shebang and can be executed directly on *nix systems after setting executable bit (chmod +x index.js), but the recommended way is via node.

## How to run the project
From the test-app directory run:

- Using npm:
  - npm start

- Or directly with Node:
  - node index.js

Typical flow:
1. The app shows a banner and prompts to choose a category.
2. Choose how many questions (All / 3 / 5 where available).
3. Press Enter to start.
4. For each question choose the numbered option.
5. After each question you can press Enter to continue.
6. After the quiz, results are shown along with incorrect answers for review.
7. You will be prompted whether you want to play again.

Example:
- cd VgEliteaDemo/test-app
- node index.js

If you see an error about modules or import syntax, ensure you are running Node 18+ and that package.json includes "type": "module".

## Extending the quiz
- Add or edit questions:
  - Edit test-app/data/questions.json. Structure:
    - categories: { <id>: { name: "Category Name", questions: [ { question, options, answer (index), explanation } ] } }
  - Each question option index is zero-based (0 = first option).
- Add new UI behaviors:
  - Modify or extend src/input.js for richer prompts, validation, or third-party libraries (inquirer, prompts).
- Customize styling:
  - Update src/colors.js to change ANSI styles or add new convenience functions.
- Modify game behavior:
  - Update src/quiz.js: shuffle, scoring, progress bar rendering, review output, or add timers/hints.

## Notes and troubleshooting
- No external dependencies: the app uses built-in Node modules only.
- If the terminal output has no colors or shows escape codes, ensure your terminal supports ANSI and that no environment variables are stripping color output.
- For automated testing, functions are modular (Quiz is a class) and can be required/imported into test files; you may add tests and a test runner as needed.
- If you get a JSON parse error, validate the JSON file (test-app/data/questions.json) for trailing commas or formatting issues.

## Development & Contribution ideas
- Add more categories and questions
- Improve UX (keyboard navigation, arrow keys, timestamps)
- Add support for loading external question packs (YAML, remote URL)
- Add persistence to store high scores
- Add unit tests for Quiz class and input helpers

## License
- MIT (as indicated in package.json)

---

If you want, I can:
- Generate sample unit tests for the Quiz class,
- Add more questions or categories,
- Convert the input layer to use a richer prompt library (inquirer/prompts),
- Or create a CI workflow for testing. Which would you like next?