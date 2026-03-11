# Security Policy

## Reporting Vulnerabilities

If you discover a security vulnerability, please report it responsibly:

- Use [GitHub Private Vulnerability Reporting](https://docs.github.com/en/code-security/security-advisories/guidance-on-reporting-and-writing-information-about-vulnerabilities/privately-reporting-a-security-vulnerability) on this repository
- Do **NOT** open a public GitHub issue for security vulnerabilities

We will acknowledge receipt within 48 hours and provide a detailed response within 5 business days.

## Security Practices

### Authentication & Authorization

- TODO: Describe auth model (e.g., Supabase Auth, JWT, OAuth)
- TODO: Describe authorization model (e.g., RLS policies, role-based access)

### Data Protection

- TODO: Describe sensitive data handling
- TODO: Describe encryption at rest / in transit
- TODO: GDPR or compliance requirements

### Input Validation

- All user input is validated using the project-approved schema validator at system boundaries
- API endpoints never trust client-side data

## Dependencies

- Dependencies are reviewed before addition
- Lock files are committed and protected
- Regular dependency audits via `npm audit` / `pip audit`

## Sensitive Files

The following files contain secrets and must NEVER be committed:

- `.env` / `.env.local`
- TODO: Add project-specific sensitive files
