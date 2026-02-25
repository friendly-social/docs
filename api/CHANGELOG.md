# Changelog

Current version: `2025.4.1`

See [news](../news/README.md#Naming) for the first two numbers. Third number
is a patch version.

## 2025.4.1: Switching Releases Schema

No changes on backend side.

## 2026.4: Real Email Service

- Changed endpoints:
    - [/auth/email](auth-email.md)
        - Added `X-Locale` header
    - [/email/link](email-link.md)
        - Added `X-Locale` header

## 2026.3: Email Auth

- New endpoints:
    - [/auth/email](auth-email.md)
    - [/auth/login](auth-login.md)

## 2026.2: Email Linking

- New endpoints:
    - [/email/link](email-link.md)
    - [/email/confirm](email-confirm.md)
    - [/email/unlink](email-unlink.md)
- `nickname`, `description`, `socialLink`, `interest` now cannot be blank
    - They can be `null`, but they can't be a whitespace-only string.

## 2026.1: User Editing

- New endpoint: [/users/edit](users-edit.md)
- Restricted max amount of interests from unlimited to `100`
