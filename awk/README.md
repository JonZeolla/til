# awk
## Deduplication without sort
`awk` has a clean method to deduplicate files without reordering them, which is particularly useful when doing password cracking with lists which are ordered in a particular way.  For example, if you had `file1`, which is a scenario-specific wordlist and `file2` which is a generic wordlist but ordered most popular to least popular, you could create a final wordlist called `file3` which retains the `file2` ordering but doesn't contain words identified in `file1` via:
```bash
cat file1 file2 | awk '!x[$0]++' > file3
```

