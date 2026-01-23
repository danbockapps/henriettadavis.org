# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a React TypeScript web application deployed on Firebase. It's a personal/memorial website with static content (images and styling). The app is minimal and primarily serves as a frontend shell for displaying content, with Firestore backend configuration ready for expansion.

## Technology Stack

- **Frontend**: React 16 with TypeScript
- **Build Tool**: Create React App (react-scripts)
- **Deployment**: Firebase Hosting
- **Backend**: Firestore (configured but not actively used)
- **Formatting**: Prettier with opinionated rules (single quotes, no semicolons, trailing commas)
- **Git Hooks**: Husky with lint-staged for pre-commit formatting

## Common Commands

```bash
# Start development server (runs on http://localhost:3000)
npm start

# Build for production
npm build

# Run tests (watches for changes)
npm test

# Run a single test file
npm test -- App.test.tsx

# Format code with Prettier
npm run prettier --write .
```

## Code Structure

- **src/**: Source code
  - `index.tsx`: Application entry point, renders React app into DOM
  - `App.tsx`: Root React component (currently just a styled div)
  - `App.css`: Application styles
  - `index.css`: Global styles
- **public/**: Static assets (images: cover.jpg, family.png, henriettadavis.jpg, paris.jpg, together.jpg; favicon; index.html)
- **build/**: Production build output (generated, not in repo)

## Firebase Configuration

- **Project**: `henrietta-davis`
- **Hosting**: Points to `build/` directory after compilation
- **Firestore**: Configured with custom rules (firestore.rules) and indexes (firestore.indexes.json)
- **Deployment**: Use `firebase deploy` to deploy to Firebase Hosting (requires Firebase CLI and authentication)

## Development Notes

- TypeScript is strict mode enabled (`"strict": true`)
- Prettier formatting is enforced on commit via husky/lint-staged
- The app uses React 16 (older version) - consider updating if making significant changes
- Public assets (images) are static and not processed by webpack
