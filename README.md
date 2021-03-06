# Unbroken
## A module to detect broken links in Markdown files

Unbroken is a NodeJS command-line utility to detect broken links in .md files.
### Usage
`npx unbroken [options]`
The exit code represents the number of errors detected so you can use it e.g. in CI loops.

#### Options
```
C:\rnw>npx unbroken -?
Unbroken 1.0 - no more broken links in markdown!

Options

  -e, --exclusions <file>            The exclusions file. Default is .unbroken_exclusions
  -l, --local-only                   Do not test http and https links
  -d, --dir <directory>              The directory to crawl
  -i, --init                         Creates a default exclusions file if one doesn't already exist
  -a, --allow-local-line-sections    Whether links to local files are allowed to have line sections like
                                     foo.cpp#L12
  -q, --quiet
  -s, --superquiet
  -?, --help
```
  Project home: [https://github.com/asklar/unbroken](https://github.com/asklar/unbroken)

### Exclusions & suppressions
You can create a `.unbroken_exclusions` file to suppress individual errors, or to skip traversing certain directories.
Just copy/paste the error you want to suppress from the output onto the `.unbroken_exclusions` file, or add a directory prefix preceded by a !.
You can also use globs.

Example:

```
URL not found https://github.com/microsoft/react-native-windows/tree/master/current while parsing test\readme.md (HTTP 404)

!node_modules

!test\test2\test.md

!**/node_modules
```
