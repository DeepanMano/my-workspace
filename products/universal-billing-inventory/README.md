# Universal Billing & Inventory

## Purpose

A browser-based product for managing billing workflows and inventory visibility in one place.

## Current stack

- React 19
- Vite
- TypeScript

## Deferred stack

NestJS and PostgreSQL are intentionally deferred. Until that work is explicitly started, use local fixtures, in-memory adapters, or clearly marked mock interfaces.

## Current principles

- Keep billing calculations deterministic and testable.
- Separate money representation from display formatting; never use floating-point arithmetic for business totals.
- Make inventory changes auditable in the domain model, even when persistence is mocked.
- Keep the first UI usable without a backend connection.
- Design API boundaries as interfaces so a later NestJS service can replace mocks without rewriting UI components.

## Suggested first slices

1. App shell and navigation.
2. Product and stock list with search and filters.
3. Invoice draft flow with line items, totals, and validation.
4. Inventory adjustment flow with an activity history.
5. Replace mock adapters with a real backend in a later phase.
