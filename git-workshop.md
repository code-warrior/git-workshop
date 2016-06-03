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

### Untracked

An untracked file is one that is neither being tracked nor being ignored (discussed in the coming section). Git will not record any changes to the file, including deleting it. A file is untracked when it’s included anew in an existing repository. To add an untracked file to the repository, it must be explicitly added using `git add`.

**Note:** Adding an empty folder to a repository won’t appear as untracked until it contains a file.

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

---
