# Optional concepts tutorial

> This article was largely written by
> [Claude 3.7 Sonnet](<https://en.wikipedia.org/wiki/Claude_(language_model)#Claude_3.7>).
> If any of the content is incorrect or unhelpful, please
> [file an issue](https://github.com/dewcservices/data-engineering-upskilling/issues).

Linux is a powerful operating system that offers a wide range of utilities and
commands to help users manage their systems efficiently. This tutorial
introduces several optional but highly useful Linux concepts and commands that
can enhance your productivity, even if you don't have a background in computing.

## File searching and manipulation

### `find`

The `find` command helps you search for files and directories in a specified
location based on various criteria such as name, size, or modification time.

#### Basic usage

```bash
find /path/to/search -name "filename"
```

#### Examples

1. Find all text files in your home directory:

   ```bash
   find ~ -name "*.txt"
   ```

2. Find files modified in the last 7 days:

   ```bash
   find /home/user/documents -mtime -7
   ```

3. Find all empty files:
   ```bash
   find /path -type f -empty
   ```

### `sed`

`sed` (Stream Editor) is a powerful text processing tool that allows you to
perform operations like search, find and replace, insertion, and deletion on
text files without opening them in an editor.

#### Basic usage

```bash
sed 'operation' filename
```

#### Examples

1. Replace the first occurrence of "old" with "new" in each line:

   ```bash
   sed 's/old/new/' file.txt
   ```

2. Replace all occurrences of "old" with "new" in each line:

   ```bash
   sed 's/old/new/g' file.txt
   ```

3. Delete lines containing a specific pattern:
   ```bash
   sed '/pattern/d' file.txt
   ```

### Combining `find` and `sed`

You can use `find` and `sed` together to search for files and perform text
operations on them:

```bash
find /path -name "*.txt" -exec sed 's/old/new/g' {} \;
```

This command finds all text files in the specified path and replaces all
occurrences of "old" with "new" in each file.

## Process management

Linux allows you to monitor and manage running processes using various commands.

### `ps`

The `ps` command displays information about active processes.

#### Basic usage

```bash
ps [options]
```

#### Examples

1. Display all running processes:

   ```bash
   ps aux
   ```

2. Display processes for a specific user:
   ```bash
   ps -u username
   ```

### `top`

The `top` command provides a dynamic real-time view of the running system,
showing processes, resource usage, and system statistics.

#### Basic usage

Simply type `top` in the terminal:

```bash
top
```

#### Key controls within top

- Press `q` to quit
- Press `k` to kill a process (you'll be prompted for the process ID)
- Press `r` to renice (change priority of) a process
- Press `M` to sort by memory usage
- Press `P` to sort by CPU usage

### `kill`

The `kill` command allows you to terminate processes.

#### Basic usage

```bash
kill [options] PID
```

#### Examples

1. Terminate a process gracefully:

   ```bash
   kill 1234
   ```

2. Force terminate a process:
   ```bash
   kill -9 1234
   ```

## Disk management and archiving

### `df`

The `df` (Disk Free) command displays the amount of disk space available on the
file system.

#### Basic usage

```bash
df [options]
```

#### Examples

1. Display disk space in human-readable format:

   ```bash
   df -h
   ```

2. Display information for a specific filesystem:
   ```bash
   df -h /home
   ```

### `tar`

The `tar` command is used to create, maintain, modify, and extract files
archived in the tar format.

#### Basic usage

```bash
tar [options] [archive-file] [file or directory to be archived]
```

#### Examples

1. Create a tar archive:

   ```bash
   tar -cvf archive.tar /path/to/directory
   ```

2. Extract a tar archive:

   ```bash
   tar -xvf archive.tar
   ```

3. List the contents of a tar archive:
   ```bash
   tar -tvf archive.tar
   ```

### `gzip`

The `gzip` command compresses files to reduce their size.

#### Basic usage

```bash
gzip [options] filename
```

#### Examples

1. Compress a file:

   ```bash
   gzip file.txt
   ```

   This will create `file.txt.gz` and remove the original file.

2. Decompress a file:

   ```bash
   gzip -d file.txt.gz
   ```

3. Compress a file while keeping the original:
   ```bash
   gzip -c file.txt > file.txt.gz
   ```

### Combining `tar` and `gzip`

Often you'll want to create a compressed archive:

```bash
tar -czvf archive.tar.gz /path/to/directory
```

To extract a compressed archive:

```bash
tar -xzvf archive.tar.gz
```

## Network diagnostics

### `ping`

The `ping` command is used to test the reachability of a host on an Internet
Protocol (IP) network.

#### Basic usage

```bash
ping [options] hostname or IP address
```

#### Examples

1. Basic ping:

   ```bash
   ping google.com
   ```

2. Limit the number of packets sent:

   ```bash
   ping -c 5 google.com
   ```

3. Change the interval between packets:
   ```bash
   ping -i 2 google.com
   ```
   This sends a packet every 2 seconds.

## Conclusion

These Linux commands provide powerful functionality that can help you manage
your system more effectively. While they may seem complex at first, regular
practice will make them second nature. Start with simple use cases and gradually
explore more advanced options as your comfort level increases.
