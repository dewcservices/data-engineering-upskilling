# Environment Variables 101

> This article was largely written by
> [Claude 3.7 Sonnet](<https://en.wikipedia.org/wiki/Claude_(language_model)#Claude_3.7>).
> If any of the content is incorrect or unhelpful, please
> [file an issue](https://github.com/dewcservices/data-engineering-upskilling/issues).

Environment variables are a fundamental concept in Linux systems like Ubuntu,
but they can be confusing if you're new to computing. Let's explore what they
are, why they matter, and how to use them effectively.

## What is an environment variable?

Think of environment variables as entries in a digital address book on your
computer. Just as an address book stores names alongside their corresponding
contact details, your computer maintains an address book of important system
information.

Each entry in this address book has two parts:

- A NAME (usually in UPPERCASE) that works like a contact name
- A VALUE that contains the actual information, like the contact details

For example, when you open a terminal in Ubuntu, there's an environment variable
called `HOME` that contains the location of your home folder (like
`/home/yourusername`). This helps programmes know where to store your personal
files.

## Why do we use environment variables?

Environment variables serve several important purposes:

1. **They provide system information**: Programmes need to know things like
   where to find important files or what language you prefer.

2. **They control programme behaviour**: Many programmes check environment
   variables to determine how they should work.

3. **They enhance security**: Storing sensitive information (like API keys) in
   environment variables keeps them out of your code.

4. **They make programmes more flexible**: Instead of hard-coding values,
   programmes can adapt based on environment variables.

5. **They allow customisation**: You can change how your Ubuntu system works by
   modifying environment variables.

## Common environment variables in Ubuntu

Your Ubuntu system already has many environment variables set. Here are some
important ones:

- `HOME`: The path to your home directory
- `USER`: Your username
- `PATH`: A list of directories where the system looks for programmes
- `LANG`: Your language and locale settings

## How to see environment variables

To see all the environment variables currently set in your terminal, open a
terminal window and type:

```bash
env
```

This will show a long list of variables and their values.

To check just one specific environment variable, use `echo` with the variable
name preceded by a `$`:

```bash
echo $HOME
```

This will display the value of your HOME variable (likely something like
`/home/yourusername`).

## What is the purpose of `export` in environment variables?

The `export` command is crucial for understanding how environment variables work
in Ubuntu. Here's what it does:

1. **Makes variables available to other programmes**: When you create a variable
   in your terminal without `export`, it's only available in that specific
   terminal session. Using `export` makes it available to other programmes you
   run from that terminal.

2. **Passes variables to child processes**: In computing terms, when one
   programme starts another programme, the second one is called a "child
   process." The `export` command ensures that environment variables are passed
   down to these child processes.

Here's the difference:

Without `export`:

```bash
MY_VARIABLE="Hello World"
bash -c 'echo $MY_VARIABLE'  # This will print nothing
```

With `export`:

```bash
export MY_VARIABLE="Hello World"
bash -c 'echo $MY_VARIABLE'  # This will print "Hello World"
```

In the first example, the new bash process (child) can't see the variable. In
the second example, because we used `export`, the child process can see it.

## How to create and modify environment variables

To create a temporary environment variable that lasts only for your current
terminal session:

```bash
export MY_VARIABLE="some value"
```

You can then use this variable in commands:

```bash
echo $MY_VARIABLE
```

## Making environment variables permanent

Variables created with `export` only last until you close the terminal. To make
them permanent, you need to add them to configuration files.

For user-specific variables, add them to the `.bashrc` file in your home
directory. The `.bashrc` file is covered in more depth in
[Understanding .bashrc](./bashrc.md).

1. Open the file in VSCode:

   ```bash
   code ~/.bashrc
   ```

2. Add your export statement at the end of the file:

   ```bash
   export MY_VARIABLE="some value"
   ```

3. Save the file and exit.

4. To apply the changes immediately:
   ```bash
   source ~/.bashrc
   ```

## Practical examples

Let's look at some practical examples of using environment variables:

1. **Adding a folder to your PATH**:

   ```bash
   export PATH="$PATH:/home/yourusername/my-scripts"
   ```

   This adds a folder to the places Ubuntu looks for programmes.

2. **Setting a default editor**:

   ```bash
   export EDITOR="code"
   ```

   This tells Ubuntu to use VSCode as your default text editor.

3. **Setting API keys for development**:
   ```bash
   export API_KEY="your-secret-key"
   ```
   This allows you to access the key in programmes without putting it directly
   in your code.

## Summary

Environment variables are like entries in a digital address book that your
Ubuntu system and programmes use to look up important information. The `export`
command makes these address book entries visible to other programmes and
processes you start from your terminal.

By understanding environment variables, you gain more control over how your
Ubuntu system works, and you can customise it to better suit your needs.
