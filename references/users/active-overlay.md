# Active User Overlay

This file is the architecture-level entry point for whichever user overlay is active in a given installation.

Public-package default:

- no user-specific overlay is bound by default

Recommended use:

1. create or choose a user overlay under `references/users/<user-name>/preferences.md`
2. update this file locally for that installation
3. keep the public package itself neutral

Example overlays may exist in this package for demonstration.
They are not package-level defaults.
