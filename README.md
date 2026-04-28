# Gentoo dwl setup (no dots)

Minimal, opinionated setup for Gentoo with **dwl**.

This is **not** a dotfiles repo.
This is a **manual reproducible snapshot** of my system.

## Philosophy

* No automation
* No install scripts
* No hand-holding

If you use this, you are expected to:

* read configs
* understand what you copy
* adapt it to your system

## What’s inside

* `make.conf`
* `/etc/portage/savedconfig/...` (dwl, foot)
* dwl patches (only patches, no binaries)
* package list (everything required to run this setup)

## What’s NOT inside

* No dotfiles (`~/.config`, etc.)
* No scripts
* No installers
* No “one command setup”

## Why?

1. Personal backup of working environment (for me)
2. Quick restore without thinking

## How to use

There is no step-by-step guide.

General idea:

1. Install Gentoo
2. Read `make.conf`
3. Apply savedconfig files
4. Install packages from the list
5. Patch and build dwl
6. Figure out the rest

If something breaks - good. Fix it.

## Notes

* This setup assumes you are comfortable with Gentoo
* Things may be outdated or system-specific
* I don’t guarantee anything will work for you

## License

Do whatever you want with it.
