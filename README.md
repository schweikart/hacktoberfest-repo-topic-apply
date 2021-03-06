# `hfest-repo` command line tool

`hfest` is a tool that adds the `hacktoberfest` topic to every repository 
associated with a user or a GitHub org. It also creates the `invalid`, `spam` 
and `hacktoberfest-accepted` labels in your repos by default.

## Installation 

1. Download the latest release from [the releases page](https://github.com/do-community/hacktoberfest-repo-topic-apply/releases/).
2. Either move the binary to `/usr/local/bin` or run it locally.

## Create a GitHub Token

You will need a GitHub token to perform these actions on your repositories. Follow the instructions for [creating a personal access token](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/creating-a-personal-access-token) and be sure to give it `repo` access.


## Usage

To use `hfest-repo`, run:

```sh
hfest-repo -t <GITHUB_TOKEN> 
```
If you don't specify your GitHub token, the tool will look for an environment variable named `GITHUB_ACCESS_TOKEN`.

### Add Hacktoberfest topic to a user's repos
```sh
hfest-repo -t <GITHUB_TOKEN> -u <GITHUB_USER>
```

### Add Hacktoberfest topic to an organization's repos
```sh
hfest-repo -t <GITHUB_TOKEN> -o <GITHUB_ORG>
```

### Remove Hacktoberfest topic from a user/org 
```sh
hfest-repo -t <GITHUB_TOKEN> -u <GITHUB_USER>/-o <GITHUB_ORG> --remove
```

### Add an arbitrary tag to a user's/organization's repos
```sh
hfest-repo -t <GITHUB_TOKEN> -u <GITHUB_USER>/-o <GITHUB_ORG> -p fun
```

### Supported Options

```
usage: hfest-repo [<flags>]

Flags:
      --help                   Show context-sensitive help (also try --help-long and --help-man).
  -t, --access-token=ACCESS-TOKEN
                               GitHub API Token - if unset, attempts to use this tool's stored token of
                               its current default context. env var: GITHUB_ACCESS_TOKEN
  -u, --gh-user=GH-USER        github user to fetch repos of
  -o, --gh-org=GH-ORG          github org to fetch repos of
      --topic="hacktoberfest"  topic to add to repos
  -r, --remove                 Remove hacktoberfest topic from all repos Default false
  -l, --labels                 Add spam, invalid, and hacktoberfest-accepted labels to repo. Default true
      --type=public            Type of repo to filter to
```
