# Linux command basics

A short reference for navigating directories, inspecting files, and finding text. Examples use ordinary files under your home directory unless noted.

## Where am I?

```sh
pwd                 # print the current directory
ls -lah              # list files, including hidden entries, with readable sizes
cd ~/Documents       # change to Documents under your home directory
cd ..                # move to the parent directory
```

`cd` is a shell built-in. The directory used in an example must exist before you can enter it.

## Create, copy, and move

```sh
mkdir -p ~/lab/notes             # create missing parent directories too
cp notes.txt ~/lab/notes/        # copy a file into the notes directory
mv draft.txt final.txt          # rename or move a file
```

Check source and destination paths before copying or moving; an existing destination may be replaced depending on the command and options.

## Read and search

```sh
less notes.txt                         # read a file a screen at a time; press q to quit
grep -n 'ERROR' app.log                # show matching lines with line numbers
find . -type f -name '*.log' -print    # find regular files ending in .log below here
```

In the `find` example, quotes keep the `*.log` pattern from being expanded by the shell before `find` receives it.

## Remove carefully

```sh
rm -i old-file.txt    # ask before removing this file
```

Removal can be difficult or impossible to undo. Verify the path first. Avoid recursive or force-removal options until you understand their effects.

## Get help

```sh
man ls
```

Use the manual page for the command installed on your system; available options can differ between distributions and implementations.

## References

- [GNU Coreutils manual](https://www.gnu.org/software/coreutils/manual/coreutils.html)
- [Linux manual pages](https://man7.org/linux/man-pages/)
