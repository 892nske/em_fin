# Repository Guidelines

## Project Structure & Module Organization
Source files live under `src/app`, using Next.js App Router conventions: folders map to routes, `layout.tsx` defines page chrome, and shared UI bits belong in colocated subdirectories. Global styling is centralized in `src/app/globals.css`, which imports Tailwind CSS v4 utilities. Static assets (logos, icons) stay in `public/`, while configuration surfaces in `next.config.ts` and TypeScript settings in `tsconfig.json`. Review `requirements.md` for feature-specific context before changing modules.

## Build, Test, and Development Commands
Install dependencies once with `npm install`. Use `npm run dev` for a Turbopack-powered dev server with hot reload. Validate production output via `npm run build`, then confirm the optimized bundle locally with `npm run start`. When diagnosing layout issues, pair `npm run dev` with browser DevTools and Tailwind's inspector.

## Coding Style & Naming Conventions
Write TypeScript-first React components using function syntax, defaulting to server components unless browser APIs are required. Keep files and folders lowercase with hyphen separators (e.g., `landing-hero`). Prefer Tailwind utility classes for layout and theming; fall back to scoped CSS only when utilities are insufficient. Follow 2-space indentation, single quotes in JSX props when literals fit, and group imports as framework → components → styles. Run `npx next lint` before submitting if you add custom ESLint rules.

## Testing Guidelines
A formal test harness is not yet configured. Add component or integration tests alongside features using `*.test.tsx` under a `__tests__` directory, and wire them into an `npm test` script (Vitest or Jest are both acceptable) before merging. High-impact UI changes should include a manual verification checklist plus screenshots, especially for responsive layouts.

## Commit & Pull Request Guidelines
Keep commits small and focused, using imperative subjects (e.g., `Add contact form handler`). Reference related tasks in the body when applicable. For pull requests, provide a concise summary, list validation steps (`npm run build`, manual checks), and attach before/after imagery for UI work. Ensure all new routes or assets are described so reviewers can navigate changes quickly.
