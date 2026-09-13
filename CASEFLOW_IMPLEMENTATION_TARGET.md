# Caseflow implementation target

This repository is the **public design authority** for Caseflow Worker. The private Caseflow application repository remains the source of truth for real application behavior, security, data contracts, API integration, tests, and release state.

## Frontend stack

The Worker frontend target is:

- React 19
- React DOM 19
- TypeScript 6
- Vite 8
- ES modules
- pnpm workspace / monorepo
- application-owned CSS and design tokens
- Microsoft MSAL Browser / Entra sign-in
- shared Caseflow TypeScript contracts

Do not require a framework change just to recreate these screens.

## Do not introduce solely for design recreation

- Next.js
- Tailwind runtime/CDN
- Material UI
- Bootstrap
- Redux
- Zustand
- React Router
- Google Fonts CDN
- Material Symbols CDN

The production app may bundle approved assets/dependencies, but the goal is to translate the existing visual design into maintainable Caseflow-owned React components and CSS.

## Translation requirement

The existing PNG/HTML files define how Caseflow should look and behave visually.

When adapting them to the production stack:

1. preserve layout, spacing, hierarchy, color, type intent, radii, sheets, grouped rows, dock treatment, and mobile behavior;
2. preserve the screen-to-screen interaction model;
3. replace prototype-only HTML/Tailwind/CDN mechanics with idiomatic React/TypeScript/CSS;
4. do not change product design merely because a different component structure is easier to implement.

Visual fidelity is an acceptance criterion, not optional inspiration.
