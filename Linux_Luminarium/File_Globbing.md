# File Globbing

## Matching with *

- The * matches any part of the filename except for / or a leading . character. We need to change the current working directory to `/challenge`, but with at most 4 characters as the argument of `cd` command: `cd /c* && ./run`

## Matching with ?

- When it encounters a ? character in any argument, the shell will treat it as single-character wildcard
- `cd /?ha??enge && ./run`

## Matching with []

- The square brackes are, essentially, a limited form of ?, in that instead of matching any character, [] is a wildcard for some subset of potential characters, specified within the brackets
- `/challenge/run file_[absh]`

## Matching paths with []

- `/challenge/run  /challenge/files/file_[absh]`

## Mixing globs

## Exclusionary globbing
