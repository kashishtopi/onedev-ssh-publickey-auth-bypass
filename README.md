# OneDev: SSH Publickey Authentication Bypass to SYSTEM Access

CVE pending (reserved).

OneDev's SSH authenticator sets the session identity as a side effect. If a client offers the
server's own host key during publickey authentication, the identity becomes the internal
SYSTEM user, and a SYSTEM session skips all permission checks. With a custom SSH client a
normal user keeps this SYSTEM identity through the login and can then read, clone, and push
every repository on the server. Self-registration is on by default, so no prior account is
needed.

- Affected: OneDev 16.8.7 and earlier
- CWE-287 (Improper Authentication)
- CVSS 3.1: 9.1 Critical (AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:N)

Full write-up and proof of concept: **[HR-onedev-ssh-auth-bypass.pdf](HR-onedev-ssh-auth-bypass.pdf)**

## Disclaimer

This proof of concept is for authorized security testing and education only.
Test only systems that you own or have explicit permission to test. The author
takes no responsibility for misuse.
