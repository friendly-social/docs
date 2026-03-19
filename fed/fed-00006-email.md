# Email

> Author: @y9san9

Email is a way to identify a user that wants to sign-in later in their profile.

**Email is not required to use the app**.

We want to achieve game-like experience when you sign-up and immediately use the app. You can create as many accounts as you like. And you don't need to create any fake numbers, emails and other things you usually do. Since we don't have any public things we need to protect, no algorithms to protect users, no autobans and other stupid stuff.

**In the future we will support multi-accounts on a single email and vice-versa**.

## Validating

There are many articles that no one validates emails in a correct way. There are whitespaces, aliases, variables, tags that are allowed in the email. We don't do validation here.

- Email length can't be more than 2048 chars
- Email should contain '@' and '.'
- This covers a non-empty and non-whitespace string

We send a code and if the address is invalid, you will not receive it.

## Attach Flow

To attach email, you send an API request. It sends an email with validation code that user needs to enter and then you send the second API request.

## Sign-in flow

No email + password flow. Passwords have a lot of problems. I believe you should start using them only for 2-factor auth. Which is not supported in MVP.

Sign-in flow is the same as attach flow:

- You send an API request to request a code
- User receives the code and enters it in the app
- You send an API request to log in

After that, a new token is generated and returned to you.

