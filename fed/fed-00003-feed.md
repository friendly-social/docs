# Feed

Feed is the main way to meet new people in Friendly. Feed is formed based on private connections of user and their network. That way you don't have only strangers and random people that optimize their profiles for better Click Through Rate. We have 2 tiers that are called **Network** and **Extended Network** that are explained in the following text.

In feed we show all the basic info that user filled in in [their profile](fed-00002-profile-mvp.md) with additional tags.

## Network

Network is people who are direct friends of your friends. If you have 5 friends and all your friends also have 5 different friends, there are going to be 25 people there. Not very much, but these people are very close to you and therefore may be very valuable to you. That is why people from **Network** are always going to be first in your feed before **Extended Network** comes.

Since user always have some mutual friends with people from network (by definition of **Network**) they are shown with the profile itself. A more thorough recommendation system is in develpoment, but for now the more common friends you have, the more likely they are going to be first.

User can decide either to send friend request or decline user.

## Extended Network

Since we don't have many people that are in the direct network, we have to can find more people by including more degrees of separation:

- 0-degree separation: It's you
- 1-degree separation: Direct friends
- 2-degree separation: **Network**
- 3-degree separation and 4-degree separation: **Extended Network**

So **Extended Network** is friends-of-your-friends-of-your-friends and friends-of-your-friends-of-your-friends-of-your-friends. I know, it sounds messy, but in practice this forms a great community of people with similar interests. Since you don't have common friends with the people from the extended network, they are not shown. There's also an extra badge that is shown when someone is from extended network.

This completely eliminates the problem with not having enough people in the network since if we again assume that everyone has 5 unique friends, the network size is going to be `5 * 5 * 5 * 5` which is `625`. And since everyone is going to connect with each other, this will expand greatly, so in practice you should never have a screen that you don't have any suggestions.

_Note: it is not possible to have someone registered without a friend and this will be covered in the upcoming FEDs. Everyone who joins must be invited, so they are always connected to the existing graph._

## Request

When user requests a friendship with someone, a push notification is sent to the other party that was liked. Then the other user will have the first user in their feed **before** any other profile. That way we achieve a faster feedback and people don't have to wait. And suggested profile also has a badge indicating that this is a friend request.

## Decline

When user declines a friendship with someone, push notification is not sent and current user is immediately removed from the queue of the other user. However, a single decline does not lead to a forever disappearance. We use [Spaced Repetition](https://en.wikipedia.org/wiki/Spaced_repetition) algorithm to make sure we only show up profiles again after user "forgot" about them. An example of this:

- User A sees User B
- User A declines
- After a month User A sees User B again
- User A declines
- After half a year User A sees User B again
- User A declines
- After 3 years User A sees User B again
- ...

