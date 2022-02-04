# `gh query-tags` GitHub CLI extension
[GitHub CLI](https://github.com/cli/cli) extension to query the GitHub repository and print out the tags.

## Installation
```
gh extension install norio-nomura/gh-query-tags
```

## Usage

```console
$ gh query-tags --help
Query the GitHub repository and print the tags that point to the commit 
specified by hash or whose names match the pattern.

The tag with the latest commit date matching the condition will be output.
If -A/--all flag is specified, all tags matching the condition will be printed 
in order of the most recent commit date.

USAGE
  gh query-tags [[<sha1> | <pattern>] ...] [flags]

FLAGS
  -A, --all                Print all matching tags in order of the most recent
                           commit date.
  -R, --repo [OWNER/]REPO  Select repository using the [OWNER/]REPO format

INHERITED FLAGS
  --help   Show help for command

ARGUMENTS
  Arguments matching /^[0-9a-f]{7,}$/ are treated as commit hash pointed by tag,
  and the rest as regular expression patterns for tag names.

USE STANDARD INPUT
  Reads standard input, searches for words that match the hash pattern, and uses
  them as hashes.

EXAMPLES
  # print tag in apple/swift pointing commit with hash 8ae983c3480462b
  $ gh query-tags --repo apple/swift 8ae983c3480462b

  # print tag in apple/swift pointing commit with hash provided by 
  # swift -version in swiftlang/swift:nightly
  $ docker run --rm swiftlang/swift:nightly swift -version | gh query-tags --repo apple/swift

```

## Author

Norio Nomura

## License

`gh query-tags` is available under the MIT license. See the LICENSE file for
more info.
