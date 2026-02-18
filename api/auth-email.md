# /auth/email

Send email with code for authorization by email.

Sent code has time to live of 20 minutes and it is allowed to try 5 times to
guess the code.

Codes that are sent have 8 digits and it is expected to design an input view
that divides this code into 2 parts in order to better remember it: xxxx-xxxx.

- URL: `https://api.getfriend.ly/auth/email`
- Method: `POST`
- Headers:
    - `Content-Type: application/json`
    - `X-Locale: $locale`
        - `en`
        - `ru`

## Request Body

```typescript
{
   "email": string
}
```

- `email`
    - Length: `0...2048`
    - String that at least contains '@' and '.'
    - No real validation happens on that endpoint other than the code that you
      need to receive

## 400 Bad Request

If there is a validation error. This code usually means a logical error in the
implementation of SDK you are using.

## 401 Not Authorized

If provided email is unknown to our server.

## 200 Success

The code was sent to this email and the next step is calling
[/auth/login](auth-login.md) with that code provided.

## Example

```bash
curl https://api.getfriend.ly/auth/email
    --request POST \
    --header "Content-Type: application/json" \
    --data '{
        "email": "mail@example.com"
    }'
```
