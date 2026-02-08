# /email/link

- URL: `https://api.getfriend.ly/email/link`
- Method: `POST`
- Headers:
    - `Content-Type: application/json`
    - `X-User-Id: $userId`
    - `X-Token: $token`

## Request Body

```typescript
{
   "email": string
}
```

Sent code has time to live of 20 minutes.

- `email`
    - Length: `0...2048`
    - String that at least contains '@' and '.'
    - No real validation happens on that endpoint other than the code that you
      need to receive

## 400 Bad Request

If there is a validation error. This code usually means a logical error in the
implementation of SDK you are using.

## 401 Not Authorized

If provided authorization is invalid.

## 409 Conflict

If provided email is already used by other account. You have to
[unlink](email-unlink.md) it from the other account first.

## 200 Success

`email` was added as unverified email linked to current user. You need to call
[/email/confirm](email-confirm.md) to make this email associated with your
profile.

Codes that are sent have 8 digits and it is expected to design an input view
that divides this code into 2 parts in order to better remember it: xxxx-xxxx.

> [!NOTE]
> Right now no message is sent to the target email. And the code for email
> confirmation is always `1111-1111`.

## Example

```bash
curl https://api.getfriend.ly/email/link
    --request POST \
    --header "Content-Type: application/json" \
    --header "X-User-Id: $userId" \
    --header "X-Token: $token" \
    --data '{
        "email": "mail@example.com"
    }'
```

This curl request works for a user with $userId and $token.

It will link 'mail@example.com' with that user, but it is possible to relink
that email later if it is not confirmed.
