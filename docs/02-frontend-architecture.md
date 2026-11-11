# 01 — Frontend Architecture

## Purpose

The frontend is the browser-facing application. It owns presentation, interaction, navigation, and accessibility. It does not own trusted authorization decisions.

## Main components

### App entry and runtime
The HTML document and application bootstrap establish the runtime. Hydration is relevant when server-side rendering is used. A global error boundary provides a controlled failure experience.

### Routing and page composition
Organize public routes, protected routes, layouts, nested routes, 404 handling, and redirects. Route protection improves navigation and user experience, but the backend must still authorize every sensitive operation.

### Design system
Centralize design tokens for typography, colors, spacing, themes, and responsive breakpoints. This supports consistency and maintainability.

### Component library
Reusable controls can include buttons, inputs, tables, cards, dialogs, navigation, and feedback states. Keep components reusable without making them excessively generic.

### Feature/domain modules
Group product capabilities such as authentication, catalogue, checkout, profile, dashboard, search, and content. Keep feature logic close to its domain while separating presentation where useful.

### State and data fetching
Distinguish local UI state from server/cache state. Define query keys, optimistic updates, and invalidation behavior. Avoid multiple competing sources of truth.

### Forms and validation
Use schema-based validation where appropriate, field-level errors, clear submit states, anti-spam controls, and accessible labels. Client validation improves usability; the backend must validate again.

### Accessibility and UX
Support keyboard navigation, visible focus, sufficient contrast, screen readers, reduced motion, and useful empty/loading/error states.

### Assets and media
Choose suitable image formats, fonts, and icons. Use lazy loading and responsive images where appropriate, and define a media policy.

### API client
Centralize typed requests, cookie/token handling, timeouts, retries where safe, and consistent error mapping. Do not place private credentials in browser code.

### Frontend testing and quality
Use unit, component, integration, end-to-end, and visual regression tests as appropriate. Check browser/device coverage, bundle budgets, Core Web Vitals, SEO metadata, and compatibility with the Content Security Policy (CSP).

## Illustrative folder structure

```text
frontend/
├── app/
├── components/
├── features/
├── hooks/
├── lib/
│   ├── api/
│   └── validation/
├── styles/
└── tests/
```

Adapt this to the framework and project scale.

## Implementation rules

- Keep UI components reusable but not over-generalized.
- Separate feature logic from presentation where it improves clarity.
- Never trust client-side authorization.
- Design for failure, slow networks, and incomplete data.
- Make loading, empty, success, and error states intentional.
