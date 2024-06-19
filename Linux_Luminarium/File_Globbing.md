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

- We can use at most 6 characters to match exact 3 file names: `educational`, `pwning`, and `challenging`: `/challenge/run [pec]*`

## Exclusionary globbing

- If the first character in the brackets is a ! or (in newer versions of bash) a ^, the glob inverts, and that bracket instance matches characters that aren't listed
- **NOTE**: The ! character has a different special meaning in bash when it's not the first character of a [] glob, so keep that in mind if things stop making sense! ^ does not have this problem, but is also not compatible with older shells
- Run /challenge/run with all files that don't start with `p`, `w`, or `n`: `/challenge/run [!pwn]*`
