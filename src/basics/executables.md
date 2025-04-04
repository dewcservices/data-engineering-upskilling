# Understanding Executables and `chmod`

> This article was largely written by
> [Claude 3.7 Sonnet](<https://en.wikipedia.org/wiki/Claude_(language_model)#Claude_3.7>).
> If any of the content is incorrect or unhelpful, please
> [file an issue](https://github.com/dewcservices/data-engineering-upskilling/issues).

When working with Ubuntu, you'll often need to run your own programs or scripts.
Let's explore executables and the `chmod` command.

## What are executable files?

Executable files are programs or scripts that can be run by your computer's
operating system. They contain machine code (in the case of compiled programs)
or script instructions (in the case of shell scripts, Python scripts, etc.) that
tell the computer exactly what operations to perform.

In Ubuntu, executables typically fall into two categories:

- **Binary executables**: Pre-compiled programs written in languages like C or
  C++
- **Script files**: Text files containing commands in languages like Bash,
  Python, or Perl

Files need specific permissions to tell the system "this file is allowed to run
as a program."

## How permissions work in Ubuntu

Ubuntu uses a permission system with three sets of permissions:

- **Owner permissions**: What the file's owner can do
- **Group permissions**: What users in the file's group can do
- **Others permissions**: What everyone else can do

For each set, there are three possible permissions:

- **Read (r)**: Permission to view the file's contents
- **Write (w)**: Permission to modify the file
- **Execute (x)**: Permission to run the file as a program

## What is chmod?

The `chmod` command (short for "change mode") is your tool for modifying these
permissions. It allows you to control who can read, write, or execute your
files.

## Viewing current permissions

To see the current permissions of a file:

```bash
ls -l myscript.sh
```

This might show something like:

```
-rw-r--r-- 1 username groupname 2048 Apr 4 14:30 myscript.sh
```

The first 10 characters show the permissions:

- First character (`-`) indicates it's a regular file
- Next three (`rw-`) are owner permissions (read, write, no execute)
- Next three (`r--`) are group permissions (read only)
- Last three (`r--`) are others permissions (read only)

## Making files executable with chmod

To make a file executable:

```bash
chmod +x myscript.sh
```

After running this command, your file permissions might look like:

```
-rwxr-xr-x 1 username groupname 2048 Apr 4 14:30 myscript.sh
```

## Two ways to use chmod

### 1. Symbolic mode

Uses symbols to add (+), remove (-), or set (=) permissions:

```bash
chmod u+x file    # Add execute permission for the owner
chmod a+x file    # Add execute permission for everyone (same as +x)
```

Where:

- `u` = user (owner)
- `g` = group
- `o` = others
- `a` = all

### 2. Numeric mode

Uses numbers to set exact permissions:

```bash
chmod 755 file    # rwxr-xr-x (owner can do everything, others can read and execute)
chmod 644 file    # rw-r--r-- (owner can read and write, others can only read)
```

Each digit represents permissions for owner, group, and others:

- 4 = read
- 2 = write
- 1 = execute
- 0 = no permissions

## Running executable files

Once a file is executable, you can run it:

1. **Using the full path**:

   ```bash
   /home/username/scripts/myscript.sh
   ```

2. **From the current directory**:
   ```bash
   ./myscript.sh
   ```

The `./` prefix is important when running files from the current directory.

## Summary

Executable files are programs or scripts that contain instructions for your
computer to execute. The `chmod` command controls who can execute, read, or
write files on your Ubuntu system. Remember that making files executable grants
them the ability to perform actions on your system, so be cautious when making
files executable from untrusted sources.
