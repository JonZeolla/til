# make
## Makefiles are like onions
Makefiles are like onions, they have layers.  It can get tricky to remember what format a command or variable needs to be to be properly escaped.

| Layer             | Variables       | Commands      |
| ----------------- | :-------------: | :-----------: |
| Makefile          | `$(variable)`   | `command`     |
| Host              | `$${variable}`  | `$$(command)` |
| Container on Host | `\$${variable}` | `\$$(command) |

## Troubleshooting
To troubleshoot `make`, use `-n` (aka `--just-print`) first, and `-d` if necessary, like:
```bash
make rule_here -n
make rule_here -d
```

