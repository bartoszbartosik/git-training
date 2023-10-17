# Initialization

## Global settings

Setting local machine's global username and email address:

```
git config --global user.name "Bartosz Bartosik"
git config --global user.email "babosz189@gmail.com"
```

Showing a list of configuration parameters in order to verify introduced changes:

```
git config --list
```

## Local repository

Initializing a local repository with a branch named "main":

```
git init -b main
```

Initializing a local repository with a default branch named "master" and moving it to a new branch named "main":

```
git init
git branch -M main
```

# Creating a project

## ReadMe file

Creating a first, ReadMe.md, file in a project directory:

```
type nul > ReadMe.md
```

## Subdirectory

Creating a CSS subfolder in a working tree and attempting to perform _git add_ on it will result in failure. This is because Git doesn't track empty directories. In case there is a desire to track the empty folder, a common convention is to create an empty file, often called _.git-keep_, in a placeholder directory.

```
mkdir CSS
cd CSS
type nul > .git-keep
```

## Staging

Staging all project files, but ignoring removed from the working tree ones:

```
git add .
```

Staging all project files, including removed from the working tree ones:

```
git add -A
```

Stage specific file:

```
git add index.html
```

## Commits

Saving changes by performing a commit:

```
git commit -m "Created an empty ReadMe.md file"
```

A commit message can have multiple lines. The first line should have no more than 50 characters and should be followed by a blank line. Subsequent lines should have no more than 72 characters. These requirements aren't firm, and they harken back to the days of punch cards and "dumb" terminals, but they do make git log output look better.

Amending a commit without changing its commit message:

```
git commit --amend --no-edit
```

Staging & committing files simultaneously:

```
git commit -a -m "Updated ReadMe.md file"
```

## Removing files

Deleting the file from a disk, but having a Git record of the file deletion in the index:

```
git rm <file_name>
```

## Reverting changes

If the file was removed using the _git rm_ command, it cannot be retrieved using the way below:

```
git rm index.html
git checkout -- index.html
```

# Investigating changes

Checking against new changes in a working tree:

```
git status
```

Showing information about the previous commits:

```
git log [--oneline] [-nX]
```

The _--oneline_ option will print the previous commits in a concise form, while _-nX_ will print the previous X commits.

Showing yet unstaged changes:

```
git diff
```

Showing changes made in comparison to the last commit:

```
git diff HEAD^
```

**Note**: in order to get help or quit from preview the above commands show, use _:h_ for former and _:q_ for latter.

# Creating a GitHub remote

Creating a remote directory:

```
git remote add origin https://github.com/bartoszbartosik/git-training.git
```

Pushing changes to the remote repository:

```
git push -u origin main
```
