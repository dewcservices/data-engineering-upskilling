# Version control with Git

## What are Git and GitHub?

[Git](https://git-scm.com/) is a tool that helps you track changes to your files
over time. Think of it as a sophisticated "save" system that remembers every
version of your work.

[GitHub](https://github.com/) is a website that hosts Git repositories
(collections of files) online, making it easier to collaborate with others.

## Hello GitHub

Start with the following tutorials from GitHub. By the end of these tutorials
you should have a repository called `hello-world` in GitHub.

- [Learn about GitHub and Git](https://docs.github.com/en/get-started/start-your-journey/about-github-and-git)
- [Create a GitHub account](https://docs.github.com/en/get-started/start-your-journey/creating-an-account-on-github)
- [GitHub Hello World](https://docs.github.com/en/get-started/start-your-journey/hello-world)

## Synchronising between GitHub and our local filesystem

When working with GitHub, we typically:

1. Clone a repository to our local filesystem
2. Create a new branch
3. Make changes to files on this new branch
4. Commit our changes
5. Push the new branch back up to GitHub
6. Raise a pull request to have our changes merged with the main branch (similar
   to the
   [previous tutorial](https://docs.github.com/en/get-started/start-your-journey/hello-world#step-4-open-a-pull-request))

### Private repositories and SSH

You will often work with private GitHub repositories. We typically use a method
called SSH to clone private repositories. Follow
[this guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent?platform=linux)
to create an SSH key and upload it to GitHub.

Go to your repository in GitHub. There should be a big green button that says
Code. Press this button. Click the "SSH" tab and copy the link. The link should
roughly have the format:

```
git@github.com:<your_username>/hello-world.git
```

Bring up a new terminal in VSCode. In the new terminal, run:

```
git clone <your-repo-link>
```

Within VSCode, you can now run:

```
code -r hello-world
```

This will reopen your current window inside of the `hello-world` repository.

Now you have a GitHub repository, let's try editing files.

### Installing Git on Ubuntu

1. Open Terminal (press Ctrl+Alt+T)
2. First, check if Git is already installed:

```

git --version

```

3. If Git is installed, you'll see a version number (e.g., "git version 2.34.1")
4. If Git is not installed, you'll see an error message. In that case, install
   Git with:

```

sudo apt update && sudo apt install git

```

5. When prompted, enter your password
6. Type 'Y' to confirm installation

### Setting Up Git

1. Open Terminal
2. Set your name (replace "Your Name" with your actual name):

```

git config --global user.name "Your Name"

```

3. Set your email (use the same email as your GitHub account):

```

git config --global user.email "your.email@example.com"

```

### Downloading (Cloning) the Repository to Your Computer

1. On your repository page, click the green "Code" button
2. Copy the URL that appears
3. Open Terminal
4. Navigate to where you want to store the project (e.g., Documents folder):

```

cd ~/Documents

```

5. Clone the repository:

```

git clone https://github.com/<your-username>/hello-world.git

```

6. Navigate into your project folder:

```

cd my-first-project

```

## Opening the Project in VSCode

1. In Terminal, make sure you're in your project folder, then type:

```

code .

```

(The period means "current folder") 2. VSCode should open with your project
files

## Making Changes and Committing

1. In VSCode, open the README.md file
2. Add some text, for example: "This is my first GitHub project"
3. Save the file (Ctrl+S)

Now let's tell Git about these changes:

4. In VSCode, click on the Source Control icon in the left sidebar (it looks
   like a branch)
5. You'll see your changed file listed
6. Click the "+" icon next to the file to stage it
7. Type a commit message in the text box at the top (e.g., "Update README with
   project description")
8. Click the tick icon (✓) to commit the changes

## Uploading (Pushing) Changes to GitHub

1. In VSCode, click the three dots (⋯) in the Source Control panel
2. Select "Push" from the menu
3. If prompted, enter your GitHub username and password or token

## Working with Branches

Branches let you work on different versions of your repository at the same time.

### Creating a New Branch

1. In VSCode, click on the current branch name shown in the bottom-left corner
   (it should say "main")
2. Select "Create new branch" from the menu that appears
3. Enter a name for your branch (e.g., "feature-about-page")
4. Press Enter

### Making Changes on Your Branch

1. Edit or create files as needed
2. Stage and commit your changes as before

### Pushing Your Branch to GitHub

1. In VSCode, click the three dots (⋯) in the Source Control panel
2. Select "Push" from the menu
3. If asked about the upstream branch, click "OK"

## Creating a Pull Request

A pull request lets you (or others) review changes before adding them to the
main project.

1. Go to your repository on GitHub
2. You should see a message about your recently pushed branch with a "Compare &
   pull request" button
3. Click that button
4. Add a title and description explaining your changes
5. Click "Create pull request"

## Merging a Pull Request

1. On your pull request page, scroll down to see details about your changes
2. If everything looks good, click the "Merge pull request" button
3. Click "Confirm merge"
4. (Optional) Click "Delete branch" to clean up

## Updating Your Local Repository

After merging changes on GitHub, update your local copy:

1. In VSCode, switch back to the main branch by clicking the branch name in the
   bottom-left corner and selecting "main"
2. Click the refresh icon (↻) in the Source Control panel, or use the three dots
   (⋯) menu and select "Pull"

## Essential Git commands

While you can do most things with VSCode's interface, here are some useful
terminal commands:

- Check repository status: `git status`
- See commit history: `git log`
- Pull latest changes: `git pull`
- Switch branches: `git checkout branch-name`
- Create and switch to a new branch: `git checkout -b new-branch-name`

## Final tips

- Commit often with clear messages
- Pull before you push to avoid conflicts
- Create branches for new features or fixes
- Never put passwords or sensitive information in your repository

## Extension tasks

- Learn more about Git branching using this
  [interactive tutorial](https://learngitbranching.js.org/)
- Fork the repository for
  [this curriculum](git@github.com:dewcservices/data-engineering-upskilling.git).
  Make some changes, and then raise a PR back to the main instance. This
  curriculum is hosted at
  [https://github.com/dewcservices/data-engineering-upskilling](https://github.com/dewcservices/data-engineering-upskilling).
  The SSH link for this repository is:
  `git@github.com:dewcservices/data-engineering-upskilling.git`
