# AI Workspace Development Rules

These rules are intentionally tool-agnostic so they can be used with any AI coding assistant, IDE agent, or human contributor.

## 1. Before changing code

- Read `AGENTS.md`, this file, and the relevant product brief.
- Inspect the existing files before proposing a new abstraction.
- State assumptions when requirements are ambiguous.
- Keep each change focused and easy to review.
- Do not add dependencies, services, or infrastructure without a clear reason.

## 2. Product boundaries

- Universal Billing & Inventory currently means a frontend product only: React 19 + Vite + TypeScript.
- Dear Diary currently means a client-first Next.js product: Next.js + TypeScript + IndexedDB + Web Crypto API + user-owned cloud storage.
- NestJS and PostgreSQL are later-phase technologies. Do not implement them now.
- Do not silently merge the two products into a shared runtime. Share conventions and small, well-defined packages only when that reduces duplication without coupling product behavior.

## 3. Implementation standards

- Prefer simple, explicit code over premature frameworks or abstractions.
- Use strict TypeScript. Avoid `any`; if an escape hatch is unavoidable, document why and keep it local.
- Keep UI, domain logic, persistence, and integration boundaries separate.
- Validate external input at the boundary and use typed internal models.
- Make loading, empty, error, and offline states intentional.
- Preserve accessibility: semantic HTML, keyboard support, visible focus, useful labels, and sufficient contrast.
- Treat user data as sensitive by default. Never log secrets, diary content, tokens, or full payment records.
- Use environment variables only for configuration; never commit secrets.

## 4. Security and privacy

- For Dear Diary, Web Crypto API is the source of truth for cryptographic operations. Never invent custom cryptography.
- Keep encryption keys out of logs, URLs, committed files, and ordinary localStorage.
- Treat IndexedDB as durable local data, not as a security boundary.
- Make cloud sync opt-in and explicit. Preserve user ownership and portability of data.
- For billing and inventory, avoid storing or handling payment-card data in the frontend.
- Review permissions and data flows before adding analytics, third-party SDKs, or cloud integrations.

## 5. Testing and verification

- Add or update tests for changed behavior, especially domain rules, persistence, encryption boundaries, and synchronization.
- Run the narrowest relevant checks first, then the full available check before handoff.
- At minimum, verify formatting, type-checking, linting, and tests when those scripts exist.
- Do not claim a check passed unless it was actually run.
- If a check cannot run, report the exact blocker and the command that failed.

## 6. Git and change hygiene

- Use small, descriptive commits when committing is requested.
- Do not rewrite history or discard unrelated user changes.
- Do not commit generated build output, local databases, secrets, editor state, or dependency folders.
- Pull requests should explain what changed, why, how it was verified, and any follow-up work.

## 7. Definition of done

A change is ready when the requested behavior is implemented, the relevant product boundary is respected, checks are run and reported, documentation is updated when behavior or setup changes, and no secrets or unrelated files are included.
