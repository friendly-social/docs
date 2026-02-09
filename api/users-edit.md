# /users/edit

- URL: `https://api.getfriend.ly/users/edit`
- Method: `PATCH`
- Headers:
    - `Content-Type: application/json`
    - `X-User-Id: $userId`
    - `X-Token: $token`

## Request Body

```typescript
{
   "nickname": {
       "value": string
   },
   "description": {
       "value": string
   },
   "interests": {
       "value": string[]
   },
   "socialLink": {
       "value": string?
   },
   "avatar": {
       "value": FileDescriptor?
   }
}
```

All fields are optional. **To change field, it is required to pass an object
with a single `value` property inside. Raw values are rejected.** It helps to
distinguish between explicit `null` and absent value. That is just much easier
to implement in majority of languages.

- `nickname`
    - Length: `1...256`
- `description`
    - Length: `1...1024`
    - Nullable
- `socialLink`
    - Length: `1...2048`
    - Nullable
    - There is no server validation whether this is a valid link
- `interests`
    - Max Amount: `100`
    - Length of each: `1..64`
- `avatar`
    - Obtained via `/files/upload`

## 400 Bad Request

If there is a validation error. This code usually means a logical error in the
implementation of SDK you are using.

## 401 Not Authorized

If provided authorization is invalid.

## 200 Success

If user edit was successful.

## Example

```bash
curl https://api.getfriend.ly/users/edit
    --request PATCH \
    --header "Content-Type: application/json" \
    --header "X-User-Id: $userId" \
    --header "X-Token: $token" \
    --data '{
        "nickname": {
            "value": "New Nickname"
        },
        "socialLink": {
            "value": null,
        },
        "avatar": null,
    }'
```

This curl request works for a user with $userId and $token.

It will:

- Set `nickname` to be `"New Nickname"`
- Set `socialLink` to be `null`
- **Will do nothing with `avatar`** and the rest of the omitted values
