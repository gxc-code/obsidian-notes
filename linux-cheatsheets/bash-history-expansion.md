# Bash History Expansion with !

## Event designators
- `!!` — previous command
- `!-3` — command 3 back
- `!42` — history entry 42 (`history` shows numbers)
- `!grep` — most recent command starting with `grep`
- `!?conf?` — most recent command containing `conf`
- `!#` — the line typed so far
- `^old^new^` — quick replace in previous command

## Word designators (append after a colon)
- `!!:0` — the command name of the previous command
- `!!:^` — first arg of previous
- `!!:$` or `!$` — last arg of previous
- `!!:*` or `!*` — all args of previous
- `!!:1-3` — args 1 through 3
- `!?conf?:%` — the word that matched `conf` in that found command

## Modifiers (append after another colon; chainable)

- `:p` — print the expansion, don’t run
- `:q` — quote the words for safe reuse
- `:h` — dirname (head) of a path
- `:t` — basename (tail) of a path
- `:r` — strip file extension
- `:e` — keep only file extension
- `:s/old/new/` — substitute first match
- `:gs/old/new/` — substitute all matches

## Practical combos

- `sudo !!` — rerun last command with sudo
- `mv !$ /tmp/` — move the last arg to /tmp
- `vim !?nginx?:$` — open the last arg of the last command that mentioned “nginx”
- `!!:p` — dry-run and inspect before executing
- `!!:s/dev/prod/` — rerun last command with a single token swapped

## Controls and gotchas

- Toggle feature: `set -o histexpand` (on), `set +o histexpand` (off)
- Escape a literal bang: `\!` or use single quotes (double quotes still expand)
- Not supported in fish; zsh supports it with similar syntax.