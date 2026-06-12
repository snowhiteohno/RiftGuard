# RiftGuard

Security analysis for the modern AI application stack.

RiftGuard is a security scanner built specifically for AI products deployed on Next.js, Supabase, Vercel, and AI SDK based architectures.

Traditional static analysis tools were not designed for the failure modes introduced by AI applications. RiftGuard focuses on the security issues teams actually ship to production, including exposed API keys, missing authorization layers, prompt injection sinks, unsecured LLM endpoints, and misconfigured Supabase deployments.

## What RiftGuard Detects

### Secrets Exposed to the Client

Detects:

- API keys bundled into client-side code
- Environment variable leaks
- Public exposure of private credentials
- Hardcoded secrets

### Supabase Security Issues

Detects:

- Tables without Row Level Security
- Overly permissive policies
- Public data access paths
- Missing authorization checks

### API Route Vulnerabilities

Detects:

- Unauthenticated endpoints
- Missing session validation
- Authorization bypass opportunities
- Excessive trust in client-supplied data

### AI-Specific Risks

Detects:

- Prompt injection sinks
- Unsafe tool execution paths
- User-controlled system prompts
- LLM endpoints without rate limiting
- Sensitive data exposure to models

## Example Output

```bash
[HIGH] Exposed Secret
app/dashboard/page.tsx:41

NEXT_PRIVATE_API_KEY detected in client bundle

Recommended Fix:
Move secret access to a server-only route.
```

```bash
[CRITICAL] Missing RLS
public.user_profiles

Row Level Security is disabled.

Recommended Fix:
Enable RLS and define access policies.
```

## Supported Platforms

| Platform | Support |
|-----------|----------|
| Next.js | ✓ |
| Supabase | ✓ |
| Vercel | ✓ |
| AI SDK | ✓ |
| TypeScript | ✓ |
| JavaScript | ✓ |

## CI Integration

RiftGuard can run locally during development or automatically inside pull requests through GitHub Actions.

Security findings can be configured to fail builds above a chosen severity threshold.

## Roadmap

- Automated remediation suggestions
- AI threat modeling reports
- Security posture scoring
- Organization-wide policy enforcement
- Multi-repository scanning

## Philosophy

AI systems fail differently.

RiftGuard is built around the assumption that AI products introduce new attack surfaces that traditional scanners frequently overlook.

Instead of attempting to scan everything, RiftGuard focuses on the mistakes that repeatedly appear in production AI systems.

## License

MIT
