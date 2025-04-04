# `head` and `tail`

> This article was largely written by
> [Claude 3.7 Sonnet](<https://en.wikipedia.org/wiki/Claude_(language_model)#Claude_3.7>).
> If any of the content is incorrect or unhelpful, please
> [file an issue](https://github.com/dewcservices/data-engineering-upskilling/issues).

The `head` and `tail` commands are essential utilities for viewing portions of
text files quickly. They're particularly useful when working with large files
where opening the entire file would be impractical.

## The `head` command

The `head` command displays the first part of a file:

```bash
head filename.txt
```

By default, `head` shows the first 10 lines. You can specify a different number
of lines using the `-n` option:

```bash
head -n 5 filename.txt    # Shows first 5 lines
```

You can also view multiple files at once:

```bash
head file1.txt file2.txt
```

## The `tail` command

The `tail` command displays the last part of a file:

```bash
tail filename.txt
```

Like `head`, `tail` shows 10 lines by default, and you can specify a different
number:

```bash
tail -n 15 filename.txt   # Shows last 15 lines
```

A powerful feature of `tail` is the `-f` option, which follows the file as it
grows:

```bash
tail -f logfile.txt   # Shows updates in real-time (great for log files)
```

## Combining commands

You can pipe these commands together for more advanced viewing:

```bash
head -n 20 filename.txt | tail -n 5   # Shows lines 16-20
```

These simple yet powerful commands are staples in system administration, log
analysis, and general file exploration.
