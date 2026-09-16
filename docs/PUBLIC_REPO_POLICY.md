# Public Repository Policy

This repository is public. Treat every committed byte as publicly accessible.

## Never Commit

- `.env` files containing real values;
- API keys or tokens;
- production database URLs;
- JWT secrets;
- OAuth client secrets;
- SMTP passwords;
- Stripe keys or webhook secrets;
- private SSH keys;
- database dumps;
- Redis dumps;
- backup archives;
- customer/user data;
- production logs containing personal data;
- private commercial source not intended for the challenge.

## Safe to Commit

- source written specifically for the challenge;
- `.env.example` with placeholders only;
- public architecture documentation;
- benchmark scripts;
- sanitized benchmark output;
- diagrams;
- public screenshots with secrets removed;
- setup instructions.

## Before Every Push

1. inspect `git diff --staged`;
2. search for `KEY`, `SECRET`, `TOKEN`, `PASSWORD`, `DATABASE_URL`;
3. verify screenshots do not expose secrets;
4. verify generated logs contain no personal data;
5. verify no backup or dump file is staged.

## If a Secret Is Accidentally Committed

Deleting the file in a later commit is not enough.

Immediately:
1. revoke/rotate the credential;
2. remove it from Git history;
3. verify the old credential is unusable.
