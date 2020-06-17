# git
## Retrieve the latest semver tag
Get the latest semver tag, excluding pre-release and build extensions.
```bash
git describe --tags --match 'v*[[:digit:]].*[[:digit:]].*[[:digit:]]' --exclude '*[-+]*' --abbrev=0 HEAD
```

### Notes
- Because [`git describe`](https://git-scm.com/docs/git-describe)'s `--match` is based on `glob(7)`, it is not as capable as you may like it to be.  As such, the above `--match` and `--exclude` combination is not perfect.

## Retrieve tagged commits
Get a list of all commit hashes which have tags.  Append `--max-count=1` to get the most recent commit to be tagged.
```bash
git rev-list --tags
```

