# git-foreach-ref

Run command for each commit in a given range.

Useful to test a script or building before pushing to ensure each commit
compiles, tests successful, passes linting, etc.

## Usage

    git foreach-ref REF COMMAND [OPTIONS..]

when `REF` is the commit range. If not using `..` `..HEAD` is implied. It uses
`rev-list` to find commits, see `git-rev-list(1)` for details on entering ranges.

The common use-case is to just use the parent branch, e.g. `master`.

## Example

    git foreach-ref master make check

Will run `make check` for each commit starting at master up to current HEAD.
