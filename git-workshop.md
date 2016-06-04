autoscale: true
slidenumbers: true

# A Git Workshop

A thorough introduction to Git in three to four hours.

### Roy Vanegas
#### 4 June 2016

---

## What Exactly is GitHub?

GitHub is a user interface, or UI, wrapper around Git, much like Spotify is a UI wrapper around audio, or iTunes around your music. In each of these, a core technology is wrapped in a graphical user interface.

For example, consider your computer: Its operating system provides you with a graphical user interface, or GUI, for creating new folders, and the GUI in turn invokes a command line interface, or CLI, to create those new folders (`mkdir`).

---

## Installing Git

1. **Open a GitHub account** at [https://github.com/](https://github.com/)
2. **Download the GitHub client** at [https://desktop.github.com/](https://desktop.github.com/)

Step `2` installs Git at the command line, and also installs a password-less SSH key that is active only when the GitHub client is loaded.

Alternatively for Mac users, you can run the `xcode-select --install` command to install Git and other command line tools without installing the GitHub client. Choosing this option will require you to manually set up an SSH key. Read [this tutorial](http://www.essential-html.com/generating-an-ssh-key-for-mac-os-x-with-github-or-bitbucket/) on how to do it.

---

## Configure Git

### Set name

Every commit needs a username and email. Let’s initiate these settings for all repositories and start with your username:

````bash
$ git config --global user.name "Roy Vanegas"
````

Check that your username was set:

````bash
$ git config --global user.name
````

---

## Configure Git

### Set email

Now set your email:

````bash
$ git config --global user.email "roy@thecodeeducators"
````

And check:

````bash
$ git config --global user.email
````

---

## The 3 States of a File in Git’s View

Files in a Git-controlled repository can only be in one of three states: tracked, ignored, or untracked.

- **Tracked** means Git will track changes, non-changes, and stages associated with a file.
- **Ignored** means Git will explicitly ignore modifications, including deletions, of a file.
- **Untracked** means Git is unaware of a file present in a repository.

---

## The 3 States of a File in Git’s View

### Tracked

When a file has been committed to the repository (via `git add` then `git commit`), the file becomes a tracked file. It can then be in one of three states: modified, staged, or committed.

---

## The 3 States of a File in Git’s View

### Tracked — modified

Modifying a tracked file means that one or more changes were made to the file, but Git has not recorded the changes. The only way to record the changes is to stage them.

---

## The 3 States of a File in Git’s View

### Tracked — staged

Running the `git add .` command stages a file, and one or more files can be added to the staging area with this command. You can then choose to undo the staging of the changes (via `git reset`) or officially record the changes by committing them.

---

## The 3 States of a File in Git’s View

### Tracked — committed

Once staged, the changed files recorded in the staging area can now be moved into the committed state by running the `git commit -m 'MESSAGE'` command and including a brief, 50- to 60-character `MESSAGE` documenting the recorded changes.

---

## The 3 States of a File in Git’s View

### Ignored

A file is ignored when it’s listed in Git’s `.gitignore` file. (Note the `.` preceeding the file name.) Unwanted files, such as Mac OS X’s `.DS_Store` file, and folders, such as WebStorm’s `.idea` folder, would be included in `.gitignore`.

A collection of `.gitignore` files is available on [GitHub](https://github.com/github/gitignore).

---

## The 3 States of a File in Git’s View

### Untracked

An untracked file is one that is neither being tracked nor being ignored. Git will not record any changes to the file, including deleting it. A file is untracked when it’s included anew in an existing repository. To add an untracked file to the repository, it must be explicitly added using `git add`.

**Note:** Adding an empty folder to a repository won’t appear as untracked until it contains a file.

---

## The Pathways of File Changes

      Working Directory → Index (Staging Area) → Git Directory

As you work with files, their changes move between the working directory, the index, and the Git directory. Modified files live in the working directory, staged files (via the `git add` command) reside in the index, and committed files (via the `git commit` command) go in the Git directory.

---

## Checking Differences

File changes can be exposed in the working directory, the staging area, or the history of the project.

---

## Checking Differences
`git diff`

The `git diff` command shows the differences between the last committed changes and the current ones in the working directory.

---

## Checking Differences
`git diff --cached`

The flag  `--cached` shows changes placed in the staging area that have not yet been committed.  If you decide that you want to revert those changes back into the working directory, you can run `git reset`.

---

## Checking Differences
`git diff` vs `git diff --cached`

Running `git diff` shows changes in the working directory, but not the staging area. Running the command with the `--cached` flag shows what’s in the staging area, but not the working directory. Thus, these two are mutually exclusive.

---

## Checking Differences
`git log -p`

To display the entire history of a repository, run `git log -p`.

---

## Checking Differences
`git log -p <filename>`

To display the entire history of a file, run `git log -p <filename>`.

---

## Discarding Changes; Resetting a File

Use `git checkout <filename>` to discard all changes to a file and revert back to the state of the file at the last commit.

---

## Removing Files

Removing tracked files can be done in one of two ways. The first method excludes Git altogether; you simply delete files as you normally would. You still add the deleted files to the staging area as you would any other file. (Yes, you’re even required to stage deleted files.)

The second method requires the `git rm` command. When files are deleted using `git rm`, deleted files are automatically staged, saving you the trouble of carrying out the `git add` command. This is the only difference between both file removal methods.

---

## Moving Files

Moving files has the same caveats as removing files, discussed previously.

---

## Storing Changes but Not Committing Them

You may find yourself in a situation where your changes aren’t ready to be committed, but shouldn’t be discarded, either. Enter `git stash`. This command will store your changes for later retrieval. You can reclaim your changes with `git stash pop`, which deletes the changes from the stash’s cache, or `git stash apply`, which keeps the changes in the cache.

---

## Cheat Sheets

There are myriad cheat sheets online. Here are just a few:

- [Atlassian](https://www.atlassian.com/dms/wac/images/landing/git/atlassian_git_cheatsheet.pdf) PDF
- [GitHub](https://education.github.com/git-cheat-sheet-education.pdf) PDF
- [Git Tower](https://www.git-tower.com/blog/git-cheat-sheet/) HTML and other formats and languages
- [Andrew Peterson of NDP Software](http://ndpsoftware.com/git-cheatsheet.html) A fun, interactive cheat sheet

---

## Suggested Readings

- *Git for Humans* by David Demaree.
  Published by A Book Apart, which is known for publishing easy-to-understand short books that are well-designed.
- *[Pro Git](https://git-scm.com/book/en/v2)* by Scott Chacon and Ben Straub.
  **Free** in eBook formats, this is a good reference and very detailed.
- *[Git Pocket Guide](http://chimera.labs.oreilly.com/books/1230000000561/index.html)* by Richard Silverman.
  Available for **free** online, this book is a good, strong reference, and, in paperback, an easy book to carry.
- *[Version Control with Git](http://shop.oreilly.com/product/0636920022862.do)* by Jon Loeliger and Matthew McCullough.
  Every detail you’d want to know about Git is contained in this tome.
