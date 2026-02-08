# Changelog

Current version: `2026.2`

## 2026.2

- New endpoints:
    - [/email/link](email-link.md)
    - [/email/confirm](email-confirm.md)
    - [/email/unlink](email-unlink.md)
- `nickname`, `description`, `social_link`, `interest` now cannot be blank
    - They can be `null`, but they can't be a whitespace-only string.

## 2026.1

- New endpoint: [/users/edit](users-edit.md)
- Restricted max amount of interests from unlimited to `100`
