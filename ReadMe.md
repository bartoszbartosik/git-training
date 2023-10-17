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

# Creating a project

## ReadMe file

Creating a first, ReadMe.md, file in a project directory:

```
type nul > ReadMe.md
```

Staging project files:

```
git add .
```

Saving changes by performing a commit:

```
git commit -m "Created an empty ReadMe.md file"
```

A commit message can have multiple lines. The first line should have no more than 50 characters and should be followed by a blank line. Subsequent lines should have no more than 72 characters. These requirements aren't firm, and they harken back to the days of punch cards and "dumb" terminals, but they do make git log output look better.

Investigating the current Git status:

```
git status
```

Showing information about the commit:

```
git log
```

# Creating a GitHub remote

Creating a remote directory:

```
git remote add origin https://github.com/bartoszbartosik/git-training.git
```
