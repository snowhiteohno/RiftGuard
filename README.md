# RiftGuard

Vibe-code security scanner for modern AI app stacks.

RiftGuard scans the exact stack where AI products actually ship:
Next.js, Supabase, Vercel, and AI SDK.

It looks for the failure modes that quietly become incidents:
- secrets exposed in client bundles
- Supabase tables without RLS
- unauthenticated API routes
- prompt injection sinks
- LLM endpoints with no rate limiting

## Why this exists

Most scanners are generic. RiftGuard is opinionated.

It is built for teams shipping AI products fast, where the real risk is not abstract compliance noise but specific stack-level mistakes that create immediate exposure.

## Features

- Client bundle secret detection
- Supabase RLS coverage checks
- API route auth validation
- Prompt injection sink detection
- LLM rate limit checks
- CLI output for local use
- GitHub Action mode for CI enforcement

## Supported stack

- Next.js
- Supabase
- Vercel
- AI SDK

## Example

```bash
npx riftguard scan
