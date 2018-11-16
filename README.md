# ghkwe

[![GitHub release](https://img.shields.io/github/release/tkrtmy/ghkwe.svg?style=flat-square)][release]
[![Travis](https://travis-ci.org/tkrtmy/ghkwe.svg?branch=master)](https://travis-ci.org/tkrtmy/ghkwe)
[![Go Documentation](http://img.shields.io/badge/go-documentation-blue.svg?style=flat-square)][godocs]
[![MIT License](http://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)][license]

[release]: https://github.com/tkrtmy/ghkwe/releases
[license]: https://github.com/kyoshidajp/ghkw/blob/master/LICENSE
[godocs]: http://godoc.org/github.com/tkrtmy/ghkwe

**ghkwe** is **G**it**H**ub **K**ey**W**ord for **E**nterprise.

Forked from github.com/kyoshidajp/ghkw

Search how many keywords in GitHub Code by GitHub API.

## Usage

```
$ ghkwe [options...] [keyword ...]
```

### Example

Output markdown format.

```
$ ghkwe exclusion_condition exclude_condition excluded_condition
| RANK |       KEYWORD       | TOTAL |
|------|---------------------|-------|
|    1 | exclude_condition   |   272 |
|    2 | exclusion_condition |    64 |
|    3 | excluded_condition  |     2 |
```

A search condition is in the file contents, language is javascript and file size is over 1,000bytes.

```
$ ghkwe --in=file --language=javascript --size=">1000" exclude_condition exclusion_condition
```

### Options

```
--in           Add in to search term.

--language     Add language to search term.

--fork         Add fork to search term.

--size         Add size to search term.

--path         Add path to search term.

--filename     Add filename to search term.

--extension    Add extension to search term.

--user         Add user to search term.

--repo         Add repo to search term.

-d, --debug    Enable debug mode.
               Print debug log.

-h, --help     Show this help message and exit.

-v, --version  Print current version.
```

*NOTE*: Set Github Access Token which has "Full control of private repositories" scope as an environment variable `GITHUB_TOKEN`. If not set, `ghkwe` requires your Github username and password(and two-factor auth code if you are setting). Because of using [GitHub API v3](https://developer.github.com/v3/).

## Install

### Homebrew

If you have already installed [Homebrew](http://brew.sh/); then can install by brew command.

### go get

If you are a Golang developper/user; then execute `go get`.

```
$ go get -u github.com/tkrtmy/ghkwe
```

### Manual

1. Download binary which meets your system from [Releases](https://github.com/tkrtmy/ghkwe/releases).
1. Unarchive it.
1. Put `ghkwe` where you want.
1. Add `ghkwe` path to `$PATH`.

## Author

[Katsuhiko YOSHIDA](https://github.com/kyoshidajp)

## Forked by
[tkrtmy](https://github.com/tkrtmy)
