# /email/confirm

- URL: `https://api.getfriend.ly/email/confirm`
- Method: `POST`
- Headers:
    - `Content-Type: application/json`
    - `X-User-Id: $userId`
    - `X-Token: $token`

## Request Body

```typescript
{
   "code": number
}
```

- `code`
    - Length: `8 digits`
    - Always `11111111` as of now

Codes that are sent have 8 digits and it is expected to design an input view
that divides this code into 2 parts in order to better remember it: xxxx-xxxx.

You have 5 attempts and 20 minutes to guess the code.

## 400 Bad Request

If there is a validation error. This code usually means a logical error in the
implementation of SDK you are using.

## 401 Not Authorized

If provided authorization is invalid.

## 403 Forbidden

If provided code is invalid or expiried (20 minutes timeout) or max amount of
attempts reached (5).

## 200 Success

Email was linked to the provided account.

## Example

```bash
curl https://api.getfriend.ly/email/confirm
    --request POST \
    --header "Content-Type: application/json" \
    --header "X-User-Id: $userId" \
    --header "X-Token: $token" \
    --data '{
        "code": 11111111,
    }'
```

This curl request works for a user with $userId and $token.

It will link previously set email with that user, and no one can use it later
unless you [unlink](email-unlink.md) it.
