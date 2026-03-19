# Blocking QR

> This is a separate FED from Add Friend QR since previous one is already implemented in some clients. But this FED is an extension to the previous one.

There's a problem that we need to acknowledge. It's a cold start problem. Even if the app has millions of users and someone just downloads the app, they will not be able to use it.

In order if you want to get benefit from the app, you must be _very active_. And your friends must be. This is the picture that illustrates the problem:

![](fed-00005-blocking-qr-problem.png)

Even before you will be _able to test_ you need to invite someone and then they need to invite someone else. And that's to just see a single profile. Of course it will not scale that way. People will not try that hard to just test it.

That is why Friendly will utilize invite-only system. You can only sign up if someone invited you. It solves this problem and the only people who will need to deal with it are developers of the app and only once.

As a side-effect if the app will become popular, this invite system will create an additional elitism feeling which is also a positive thing.
