## What is this?
Implementation of SMART on FHIR launch flow for eClinicalWorks EHR integration. Handles OAuth2 authentication with healthcare-specific launch context and token exchange.

## Why does it exist?
Built to establish secure API integration with eClinicalWorks, a major Electronic Medical Records platform. Part of a larger effort to automate clinical workflows and enable external applications to access patient data within EHR security constraints.

## Technical approach:
Launch Flow:

LaunchPage.jsx - Receives initial launch parameters (iss, launch) from EHR, fetches server metadata, stores OAuth endpoints
CallbackPage.jsx - Handles OAuth callback, exchanges authorization code for access token

Stack: React, React Router, OAuth2 authorization code flow with SMART launch extensions

## Current state:
Status: Partial implementation. Authentication flow is coded but untested in production EHR environment.
Limitation: SMART launch requires EHR-initiated context (the iss and launch parameters must come from the actual EHR system). Full testing was not possible without access to a live eCW environment that could initiate the launch sequence. Static hosting (GitHub Pages) also presented challenges for handling OAuth secrets securely.

What works: OAuth flow logic, metadata fetching, token exchange structure
What's missing: Live EHR environment for end-to-end testing, server-side secret management

## Technologies:

- React
- React Router
- OAuth2 / SMART on FHIR
- eClinicalWorks API

## What I learned:
Healthcare API integration requires understanding industry-specific authentication protocols (SMART on FHIR) that extend standard OAuth2. Integration testing is constrained by access to live EHR environments, making development cyclic and dependent on external systems.

# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript and enable type-aware lint rules. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.
