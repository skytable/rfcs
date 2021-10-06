# RFC - 1

## Details

- **Title:** Versioning Policy
- **Date:** October 4, 2021
- **Implementation PR:** None
- **Tracking issue:** None
- **Author:** Sayan N. \<nandansayan@outlook.com\>
- **Supersedes:** None

## Summary

This RFC proposes to add a versioning policy for Skytable, enhancing reliability and highlighting our versioning guarantees.

## Motivation

Skytable is a free and open-source NoSQL database that aims to solve the problem of data modeling at scale. With Skytable's community growing everyday, it is necessary that we explicitly define our versioning policy so as to make sure that our users' data is safe and to explicitly let them know about what they can expect. Prior to this RFC, we have exemplified great interest in the safety of our users' data, through the [guaranteed backward compatibility](https://github.com/skytable/skytable/wiki/disk-storage-formats) system for disk formats which ensured that whenever a major breaking change occurred in the disk format &mdash; users from earlier versions should be able to easily upgrade their datasets to make it work with the latest format. It used to look like:

```
skyd upgrade --from <old-format-name>
```

With the release of version 0.7, it became infeasible for us to provide a backward compatibility system like above, but to respect our own commitment, we started providing the Skytable Migration Tool (`sky-migrate`) that enabled users to upgrade their datasets with ease &mdash; by reading their old data folder and migrating it over a network to the new database server.

Again, this reflects our commitment to the reliability of the database and it is fundamental for us to do so because the fact that we found an easier way to store lengths shouldn't mean that our user's data would be put at risk.

## Description

RFC 1, titled the "Versioning Policy" will describe what guarantees Skytable's versioning provides. Our versioning policy is largely inspired by [Semantic Versioning](https://semver.org), but with modifications to allow for Skytable's "release early, release often" way of delivering releases. This policy states that:

1. All versions are specified in a format similar to `x.y.z` where `x`, `y` and `z` are positive integers
2. Each of these integers have the following names:
   - `x` is called the _Major Version_
   - `y` is called the _Minor Version_
   - `z` is called the _Patch Version_
3. Versions where the _Major Version_ is greater than 0 will be called _Release Channel_ versions. For these releases, we present the **Release Channel Version Policy**:
   1. For two releases with Major Versions `x1` and `x2`, if the integer value of `x2` is greater than `x1` (i.e `x2>x1`), then the release with integer value `x2` is considered to be the more recent release. An increment in the Major Version **always indicates a breaking change**.
   2. For two releases with Minor Versions `y1` and `y2`, if the integer value of `y2` is greater than `y1` (i.e `y2>y1`), then the release with integer value `y2` is considered to be the more recent release.
   3. For two releases with Patch Versions `z1` and `z2`, if the integer value of `z2` is greater than `z1` (i.e `z2>z1`), then the release with integer value `z2` is considered to be the more recent release.
4. Versions where the _Major Version_ is equal to 0 will be called _Developer Channel_ versions. For these releases, we present the **Developer Channel Version Policy**:
   1. For two releases with Minor Versions `y1` and `y2`, if the integer value of `y2` is greater than `y1` (i.e `y2>y1`), then the release with integer value `y2` is considered to be the more recent release. An increment in the Minor Version **always indicates a breaking change**.
   2. For two releases with Patch Versions `z1` and `z2`, if the integer value of `z2` is greater than `z1` (i.e `z2>z1`), then the release with integer value `z2` is considered to be the more recent release.
5. **Breaking patch policy**:
   1. Patch versions can make breaking changes when the changes are small, but have backward-incompatible impacts. **Such releases are heavily discouraged** and **should be used as a last resort**.
   2. Patch versions that _do break_ backward compatibility should explicitly state so in the Changelog.
6. **Pre-release policy:** All versions released with tags like `alpha.<number>` or `beta.<number>` or `rc.<number>` should **not be considered stable**. These releases are called pre-releases. Examples, of such version names include: `0.7.0-alpha.1`, `0.7.0-rc.1` or `0.6.0-beta.1`.
7. This RFC also proposes a "**Guaranteed Data Compatibility Policy**".
   - This guarantees that all users from earlier versions of the database would be able to migrate their datasets to newer versions using built-in or official tools
   - This migration can be done either through a built in compatibility suite, like the one introduced in 0.6.0 for example or with a migration tool, like the one released in 0.7.0 or with any other tool that will be provided with a release

## Implementation Details

None

## Drawbacks

None

## Alternatives

One possible alternative is to continue using Semver, which doesn't put much emphasis on our "release early, release often" release cycle.

## Unresolved Questions

None

## Future possibilities

None
