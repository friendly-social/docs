# /auth/login

Generate a new token for existing account using the code that was sent via
[auth/email](auth-email.md).

- URL: `https://api.getfriend.ly/auth/login`
- Method: `POST`
- Headers:
    - `Content-Type: application/json`

## Request Body

```typescript
{
   "email": string,
   "code": number
}
```

- `email`
    - Length: `0...2048`
    - String that at least contains '@' and '.'
    - No real validation happens on that endpoint other than the code that you
      need to receive
- `code`
    - Length: `8 digits`

Codes that are sent have 8 digits and it is expected to design an input view
that divides this code into 2 parts in order to better remember it: xxxx-xxxx.

You have 5 attempts and 20 minutes to guess the code.

## 400 Bad Request

If there is a validation error. This code usually means a logical error in the
implementation of SDK you are using.

## 403 Forbidden

If provided code is invalid or expiried (20 minutes timeout) or max amount of
attempts reached (5).

## 200 Success

You guessed the code and a new token was created and linked to your account.

```typescript
{
    "id": number,
    "token": string,
    "accessHash": string
}
```

- `id`
    - Size: 64 bits
- `token`
    - Length: `256`
- `accessHash`
    - Length: `256`

## Example

```bash
curl https://api.getfriend.ly/auth/login
    --request POST \
    --header "Content-Type: application/json" \
    --data '{
        "email": "mail@example.com",
        "code": 11111111,
    }'
```
