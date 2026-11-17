# Dear Diary

## Purpose

A private diary designed around local-first writing, user-controlled encryption, and portable user-owned storage.

## Current stack

- Next.js
- TypeScript
- IndexedDB for local persistence
- Web Crypto API for cryptographic operations
- User-owned cloud storage for optional synchronization and backup

## Current principles

- Writing should work offline and remain responsive.
- Local data is the primary working copy.
- Encryption and key handling must be explicit, reviewed, and covered by tests.
- Cloud storage is user-owned and provider-agnostic at the product boundary.
- Sync must handle retries, conflicts, deletions, and partial connectivity without losing entries.
- Avoid making diary content available to analytics, logs, previews, or server rendering by default.

## Suggested first slices

1. Diary entry editor and local IndexedDB repository.
2. Entry list, search, drafts, and offline states.
3. Web Crypto API key and encryption boundary with test vectors.
4. Export/import for portability.
5. User-owned cloud storage adapter and explicit sync controls.

## Privacy boundary

Any feature that reads or transmits diary content must document where plaintext exists, which key protects it, and what happens when the device is offline or the user revokes access.
