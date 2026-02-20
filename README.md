# VgEliteaDemo — Quiz CLI

Interactive command-line quiz game built with **Node.js** and **modern JavaScript (ES Modules)**. Questions are loaded from JSON, and the app provides a simple terminal UI with scoring, progress, and review of incorrect answers.

## Key features
- Multiple quiz categories loaded from `test-app/data/questions.json`
- Choose how many questions to answer (All / 3 / 5 when available)
- Randomized question order (Fisher–Yates shuffle)
- Input validation for menu/answer selection
- Progress bar + question counter
- Final score summary with a review of incorrect answers
- No external runtime dependencies (Node.js built-ins only)

## Repository layout
```text
VgEliteaDemo/
  README.md
  test-app/
    index.js
    package.json
    data/
      questions.json
    src/
      colors.js
      input.js
      quiz.js
```

## Project description
This repo is primarily a small demo/learning project showcasing:
- ES Modules (`import` / `export`)
- Async I/O (`fs/promises`) and JSON parsing
- Simple CLI input handling using `readline`
- Small modular design (quiz engine + input + color utilities)

## Setup instructions
### Prerequisites
- **Node.js 18+** (`package.json` sets `engines.node: >=18.0.0`)

### Install
This project has no external dependencies, so `npm install` is optional.

```bash
cd test-app
npm install
```

## How to run the project
From the `test-app` directory:

```bash
npm start
# or
node index.js
```

### Typical flow
1. Choose a category
2. Choose how many questions to answer
3. Answer each question by entering the option number
4. View your results and review incorrect answers
5. Choose whether to play again

## Testing
A placeholder test script is included:

```bash
npm test
```

It runs Node’s built-in test runner (`node --test`). Add tests as needed.

## Extending the quiz
- Add/modify questions in `test-app/data/questions.json`.
  - `answer` is a **zero-based** index into the `options` array.
- Customize CLI prompts in `test-app/src/input.js`.
- Adjust styling/ANSI colors in `test-app/src/colors.js`.
- Change quiz flow, scoring, or output formatting in `test-app/src/quiz.js`.

## Troubleshooting
- If you see `SyntaxError: Cannot use import statement outside a module`, ensure:
  - You are running Node 18+, and
  - You run from `test-app/` where `package.json` sets `"type": "module"`.
- If colors look wrong, ensure your terminal supports ANSI escape codes.

## License
MIT