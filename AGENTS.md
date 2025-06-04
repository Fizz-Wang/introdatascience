
# Web-Based Board & Card Game Development Guide

## Dev Environment & Core Setup Tips
* **Tech Stack Foundation**:
    * Opt for a modern frontend framework (e.g., React, Vue) with TypeScript for robust UI development.
    * Select a backend (e.g., Node.js/Express, Python/Django) suitable for real-time game logic and API.
    * Utilize Git for version control from the start.
* **Modular Architecture**:
    * Design a modular project: separate core logic, UI, AI, and individual game modules (Chinese Chess, Go, Dou Dizhu, Blackjack) for scalability.
    * Clearly define game rules for each game before coding.
* **Initial User Flow**:
    * Develop the main menu for game selection first.
    * Implement screens for choosing player count and nicknames post-game selection.
* **Package Management**:
    * Use a consistent package manager (e.g., `pnpm`, `npm`, `yarn`) to manage dependencies across modules.
    * Ensure each game module/package has its `package.json` correctly configured.

## AI (PvE) & Multiplayer (PvP/PvPvE) Implementation Tips
* **AI for PvE**:
    * Select appropriate AI algorithms per game (e.g., Minimax/Alpha-Beta for Chess/Go; rule-based or MCTS for Dou Dizhu; basic strategy for Blackjack).
    * Implement multiple, distinct AI difficulty levels for a good player experience.
    * Design AI to be competent and challenging based on selected difficulty.
* **Multiplayer Logic**:
    * Use WebSockets for low-latency, real-time communication in PvP/PvPvE modes.
    * Implement server-authoritative game state management and synchronization.
    * Handle game session logic: player turns, disconnections, and reconnections.
* **Mode Handling**:
    * Differentiate game modes: PvE for single-player against AI; PvP or PvPvE based on player count and game design.

## UI/UX & Graphics Tips
* **Visual Appeal**:
    * Prioritize a visually appealing and "exquisite" main lobby and game interfaces.
    * Use high-quality graphics, clear iconography, and smooth animations.
* **User Experience**:
    * Ensure intuitive navigation from game selection to gameplay.
    * Design responsive layouts for various screen sizes (desktop, tablet).
    * Provide clear feedback for player actions and game state changes.

## Testing & QA Instructions
* **Comprehensive Testing Strategy**:
    * Write unit tests for core game logic (rules, scoring) and AI decision-making.
    * Develop integration tests for client-server interactions and multiplayer scenarios.
    * Conduct E2E tests simulating full gameplay loops for each game.
* **AI & Gameplay Validation**:
    * Rigorously test AI at all difficulty levels against human players and other AIs.
    * Playtest extensively to ensure game balance, fun factor, and rule adherence.
* **Quality Checks**:
    * Fix any bugs, UI glitches, or type errors until the entire suite is green.
    * Run linters and formatters (`pnpm lint --filter <project_name>`) after changes to maintain code quality.
    * Commit to adding or updating tests for any new or modified code, ensuring CI passes before merges.
* **Targeted Testing**:
    * To focus on a specific test (e.g., with Vitest): `pnpm vitest run -t "<test_name_pattern>" --filter <project_name>`.

## Deployment & Scalability Notes
* **Hosting Choices**: Select appropriate hosting for frontend (e.g., Vercel, Netlify) and backend/database (e.g., AWS, Google Cloud, Azure).
* **CI/CD Pipeline**: Set up CI/CD for automated testing, builds, and deployments.
* **Future-Proofing**: Design the overall architecture to easily accommodate new games and features with minimal refactoring.
* **Monitoring**: Implement logging and performance monitoring for live game operations.