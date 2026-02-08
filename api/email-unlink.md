# /email/unlink

- URL: `https://api.getfriend.ly/email/unlink`
- Method: `POST`
- Headers:
    - `Content-Type: application/json`
    - `X-User-Id: $userId`
    - `X-Token: $token`

## 400 Bad Request

If there is a validation error. This code usually means a logical error in the
implementation of SDK you are using.

## 401 Not Authorized

If provided authorization is invalid.

## 200 Success

`email` is not associated with current account anymore and can be linked again
to any other account later.

## Example

```bash
curl https://api.getfriend.ly/email/unlink
    --request POST \
    --header "Content-Type: application/json" \
    --header "X-User-Id: $userId" \
    --header "X-Token: $token" \
```

This curl request works for a user with $userId and $token.
It will unlink current email for that user if any.
