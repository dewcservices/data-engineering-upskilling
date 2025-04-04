# Navigating history

> This article was largely written by
> [Claude 3.7 Sonnet](<https://en.wikipedia.org/wiki/Claude_(language_model)#Claude_3.7>).
> If any of the content is incorrect or unhelpful, please
> [file an issue](https://github.com/dewcservices/data-engineering-upskilling/issues).

## Basic usage

View your command history with the simple command:

```bash
history
```

This displays a numbered list of recently used commands, with the most recent at
the bottom.

## Common options

### Limiting results

To see only the last few commands:

```bash
history 10
```

This shows just the 10 most recent commands.

### Clearing history

To erase your command history:

```bash
history -c
```

## Using the up arrow

The simplest way to recall previous commands is using the up arrow key:

- Press `↑` once to access your most recent command
- Press `↑` repeatedly to cycle through older commands
- Press `↓` to move forward through commands after going back

## Ctrl+r search

The real power comes with recursive search using `Ctrl+r`.

### Basic searching

Press `Ctrl+r` and start typing to search backwards through your command
history:

```
(reverse-i-search)`touch': touch filename.txt
```

### Navigating results

- Press `Ctrl+r` again to cycle through older matching commands
- Press `Enter` to execute the found command
- Press `Escape` to edit the command before executing
- Press `Ctrl+g` to cancel the search

## Practical applications

- Finding complex commands you've used before
- Rerunning commands without retyping them
- Searching for commands related to specific projects
- Reviewing your work from previous sessions

Using history effectively means spending less time typing repetitive commands
and more time being productive. Combined with the up arrow and `Ctrl+r`, it
becomes one of the most efficient ways to navigate your command-line workflow.
