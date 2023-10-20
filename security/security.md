# Security at Spice AI

**Last updated:** Aug 22, 2023

Spice AI's approach to security when providing services including Spice.ai, data.spiceai.io, and spicerack.org.

To report a vulnerability see: [report.md](report.md "mention")

### Principles

Spice AI takes a principled approach to security. These principles include:

* **Compliance**: Certified compliance with industry standards.
* **Secure-Access-Control:** All Spice AI systems are protected by Secure-Access-Controls including Authentication (AuthN), Authorization (AuthZ), and RBAC (Role-Based-Access-Control).
* **Data Protection:** All secret and sensitive information is encrypted in-transit and at-rest.
* **Multi-Factor-Authentication (MFA):** All authentication systems require and enforce Multi-Factor-Authentication (MFA).
* **Least Privilege:** Least-Privilege-Access is employed so that users, employees, and contractors do not have greater access than necessary.
* **Defense-in-Depth:** Multiple security controls in depth.
* **Auditable:** Access and usage is logged and auditable.
* **Secure Code:** Code is scanned and tested for secrets and vulnerabilities.
* **Just-In-Time Access:** Access is given only when it's required.

### Compliance

Spice AI is in the process of being certified for SOC2-2017 Type II, which is expected to be complete by Jan 2024.

### Secure Access Control

Spice AI corporate, development, and production systems are protected by Single-Sign-On (SSO) Secure-Access-Controls. This includes secure Authentication (AuthN) and role/group based Authorization (AuthZ).

### Data Protection

Corporate and production secrets are encrypted at-rest and in-transit. Corporate secrets are stored and managed in a enterprise-grade password manager with SSO access. Service secrets are stored and managed in platform specific secure key vaults and key stores. A minimum of TLS 1.2+ is employed for encrypted transmission.

### Multi-Factor-Authentication (MFA)

All all access requires and enforces Multi-Factor-Authentication (MFA) where possible.

### Least Privilege

Least-Privilege-Access is employed so that users and employees do not have greater access than necessary.

### Defense-in-Depth

Spice AI employs multiple levels of security, including Firewalls and Bastions for access into private networks, user, service, and machine authentication and authorization.

### Deployment Environments and Controls

Deployment environments, such as Development, Production, etc. are utilized and segregated. Controls including approvals for deploying to Production environments are used, enforced, and logged.

### Auditable

Access is logged and auditable.

### Secure Code & Patch Management

Code is scanned and tested for secrets and vulnerabilities during Continuous Integration (CI) systems, using [GitHub Security](https://docs.github.com/en/code-security) features like Dependabot, CodeQL, and Secrets Scanner. Base level operating systems and container images are monitored, upgraded, and updated on regular cycles.

### Just-In-Time Access

No-standing-access is enforced, with users only given access when required (JIT) and for a limited period of time.
