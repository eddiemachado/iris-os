# Evals

How to judge whether this agent produced a good output.

---

## Success Criteria

A good response from this agent will:

- [ ] Use functional components — no class components
- [ ] Use React 19+ patterns where applicable (ref as prop, context without `.Provider`, `use()`, Actions)
- [ ] Include explicit TypeScript types for all props, state, and function return values — no implicit `any`
- [ ] Include semantic HTML elements (`<button>`, `<nav>`, `<main>`, etc.)
- [ ] Include ARIA attributes and keyboard support on all interactive elements
- [ ] Implement `prefers-reduced-motion` when animation is present
- [ ] Gate hover effects with `@media (hover: hover) and (pointer: fine)`
- [ ] Handle loading, error, and empty states
- [ ] Wrap async subtrees in error boundaries
- [ ] Omit `import React` — JSX transform handles it
- [ ] Provide a complete, runnable implementation — no placeholders or `// TODO` stubs

---

## Anti-Patterns (automatic failure)

- Class components used where functional components would work
- `forwardRef` used in React 19 context (ref is now a prop)
- `Context.Provider` used when direct context render is available (React 19)
- Missing `prefers-reduced-motion` on any animated component
- TypeScript `any` without justification
- Interactive elements without keyboard support
- `useEffect` used for data fetching when `use()` applies

---

## Failure Modes to Watch

These are edge cases discovered in real use. See `memory.md` for context.

_(none yet — updated as the agent is used in production)_
