# Group QR

> Author: @y9san9, discussed with @alex-npmn
>
> State: Discussion
>
> **Not for MVP**

## Problem

Currently there is a problem when you want to add multiple people from specific chat or place. You have to generate code for each one who you want to add as your friend. This is intended use of such QRs since you have to review everyone manually before they get into your network. Otherwise, spam or low-quality connections could appear. But the problem is still a problem.

## Proposed Solution

Allow users to create group QR Codes. Instead of adding someone as a friend right away, by scanning this QR Code people will be able to connect with anyone else who scanned this QR Code via **Feed**.

### Scenario 1

You have a chat of close-friends and you want to add them as your friends. You create a group QR Code and display/print it everywhere. People are going to discover everyone who scanned this QR Code by going to **Feed** and find people that they are interested in.

## UX

QR Code has a **Display Name** property that user must input.

- `1..128` characters
- Required
- Not blank

### Feed

In Feed if person was suggested to you because it scanned QR Code it should be shown in the top left corner where **badges** are shown (Extended Network, Friend Request, etc.). By tapping to that badge you can leave from it.

### Group QR Codes

A popup with QR Codes (where you can create, read, update, delete them) should be in the same place where you create a QR Code to share your profile. That way both properties are achieved:

- Discoverable, user will try to share their profile and stuble upon this feature
- Doesn't take important real estate since it's not a tab in the bottom bar and this doesn't add mental overhead

## Immutability

Anyone can create a group QR Code, but no one owns it. **Display Name** can't be modified, people can't be moderated. The create of QR Code automatically joins it, later they can leave, but the QR will stay, so people can continue networking.

## Integrations

Blocking QR should allow both private QR Code and pubic QR Code.

## Time Limit

Group QRs in their first version will have a forced time-limit of 7 days. This will make QRs half-public. You will be able to print them on coferences for people to join, but there's no point in promotion and abuse since it will expire soon.

## Future Plans

This FED is keeping things minimal to make it possible to implement things fast and then iterate with the next FEDs that add more options to the existing ideas. Options that were discussed are:

- Customizing Time Limit
- Customizing Participants Limit
- Ability to revoke prematurely
- etc.

