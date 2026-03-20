# Laboratories

The development process of Friendly is unique in a sense. Everyone who works on that project has main job and therefore can't work on that project full-time. Sometimes only a few hours a week are available for a side project and that's fine. We still want to collaborate on that thing with everyone interested. For that matter a concept of 'Labs' was created.

What is a Lab? Lab is an independent research group (or a single person) that is scoped to a single research area or a project. All Labs are created equal meaning that no Lab is more important and there is no hierarchy. If someone doesn't like what a Lab is doing, they can create a new one on the same topic. A Lab can be abandoned at any point of time.

This concept helps us to maintain a consistent pace where project is always growing in several domains. We accumulate Individual Contributors and don't need to have managers and stuff. Failure of a single Lab doesn't affect other Labs. Everyone is free to try creating a new Lab with no real responsibilities since it can be abandoned at any time.

# Quarters

Project Development is divided into quarters. That is a convenient way to structure such long-running projects and without making it a routine. We have several things attached to quarters which are listed below.

## Releases

Versions of our apps use the following notation: `YYYY.Q.X`

Where:

- `YYYY` the year of release
- `Q` the quarter of the year
- `X` platform-specific release incrementor

Releases with new features are released 4 times a year (each quarter). Bug-fixes, vulnerabilities and other things that don't include new features can be released as needed to the platform lab. This makes is easy to synchronize features across projects. So devs may implement a feature with a 2-month gap yet it will be in the same release.

Alpha-channels are allowed but it's up to Laboratory what to do with them. Things like Google Play Beta Program, TestFlight, Dev Stands are fine and may be released in any way the Lab wants.

## Milestones

Each quarter Laboratories need to create a milestone that follows `YYYY.Q` convention and plan what existing features will be implemented in that quarter. Usually it is used to sync [FEDs](fed/README.md) implementation to be the same on all platforms, but other issues are also allowed.

Issues should always have 'milestone' field. If an issue has no 'due' date or searching for contributors 'Backlog' milestone should be used. Issues with no milestone are harmful since it's not clear whether it is going to be implemented soon or it is not something devs are working on.

## Abandoning Lab

If lab is not active for a quarter of the year, it is considered abandoned.

## News

Each quarter we release news. More on them here: [link](news/README.md).
