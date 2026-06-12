# Security Policy

Agent Ready Coding Loop is a framework for directing coding agents. It does not run production services by itself, but generated projects may handle sensitive data.

## Reporting Security Issues

If you find a security issue in the framework instructions, templates, or examples, please open a private security advisory if available or contact the maintainer directly.

Do not paste secrets, tokens, API keys, or private customer data into issues, pull requests, prompts, or chat transcripts.

## Framework Security Rules

Agents following this framework should:

- never commit secrets;
- never log sensitive data;
- validate untrusted input;
- treat third-party API responses and LLM output as untrusted;
- use official documentation and Context7 when available for security-sensitive APIs;
- create guardrail criteria for privacy, safety, and security requirements;
- stop and ask when a decision changes risk, cost, data use, or legal exposure.

## Token Handling

Do not paste GitHub tokens, API keys, or credentials into chat.

Use environment variables, local credential stores, or platform-approved connector permissions.

