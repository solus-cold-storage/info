Releasing
=========

![logo](https://solus-project.com/imgs/budgie-small.png)


The Budgie Desktop components shall all follow semantic versioning. Note however that the fields within `semver` hold special meaning within Budgie.

The first new Budgie Release under the new organisation, modular structure, and versioning scheme, shall start at version **11.0.0**. This will be considered the first stable release of the new Budgie Desktop.

Epoch
------

As each subsequent release is defined by series, with the potential for major changes between each series, the ``$MAJOR` field (i.e. `11.0`) is considered the epoch.

This may be bumped when base ABI has completely altered, or a refactor is involved, or it is deemed necessary to introduce new incompatabilities. At other times it may also be bumped due to new major features, such as compositor replacement, or architectural shifts.

Series
------
A series is defined as a `$MAJOR.$MINOR` version number. The stable series is always the current series. The first series shall be `11.0`, followed by `11.1`, etc.

Every component in a given series must be compatible with one another, with an agreed set of minimum version dependencies for mandatory components. i.e. it is not acceptable to bump the minimum `gtk+-3.0` requirement for any given component in a series, a new series must be created.

If shifting to new minimum dependencies introduces `#ifdef` spaghetti, or is in some other way a burden and a large change, a new epoch should instead be considered and discussed.

Patch numbering
----------------
Each update in a series affects only the `patch` number in the version. Thus a minor update to the `11.0` series would result in the version number `11.0.1`, `11.0.2`, etc. These are defined on a per component basis.

Minor releases may still add new features as long as they remain compatible with the series and do not introduce invalid minimum dependency bumping.


Branching
---------

Upon achieving a new stable release, every component should then create an appropriate branch for the current major+minor version number, to denote support for that stable series.

The first branch will be `budgie-11.0`, on a per component basis. The second will be `budgie-11.1`, and so on. This allows feature development to continue on the `master` branch, while facilitating updates to be provided in an older series. Doing so will enable the Budgie Desktop components to issue **point releases** for an older series, or indeed even the current series, while working on the next series.
