# sr-client-1
Ads for some SR client - theoretical git repo

# Clients
**Each** client gets its own repo. This repo is a dummy client.

# Jobs
**Jobs** are split out into their own branches so that when you pull down assets to work on, you get only what you need.

There are many ways these branches can be broken down. For this test, I will use 2 different approaches.

## Approach 1
**Branches** are split by Job #.

```
Job1 (checkout here)
    |____Size1
        |____OptionA
        |____OptionB
    |____Size 2
        |____OptionA
        |____OptionB

Job2 (checkout here)
    |____Size1
        |____OptionA
        |____OptionB
    |____Size 2
        |____OptionA
        |____OptionB
```

## Approach 2
**Branches** are still split by Job #, but further split by the Size.
This doesn't seem ideal due to how similar the assets would be between sizes, but it would reduce
the size per pull.

```
Job1/Size1 (checkout here)
        |____OptionA
        |____OptionB

Job1/Size2 (checkout here)
        |____OptionA
        |____OptionB

Job2/Size1 (checkout here)
        |____OptionA
        |____OptionB
        
Job2/Size2 (checkout here)
        |____OptionA
        |____OptionB
```

# Checkout Commands
**If** you are checking out a branch from a client you have never pulled down from before, you can
clone a specific branch of the repo, which will fetch all of the repos dta, making it easier to
switch to other branches in the future. This command only needs to be run locally 1 time per repo.
```
git clone -b <branch> <remote_repo>
```

### Example
```
git clone -b Job1 https://github.com/elitegoliath/sr-client-1.git
```
----
**If** you just want to switch branches on a client you've pulled a branch from before, but you have never checked out the particular branch you want, you will first want to make sure that you are up-to-date with remote, then checkout the new branch. (The -p command, which is short for --prune, will make sure that any dead branches you have fetched will get cleaned up)

Make sure to run these commands from within the directory in which the repo exists for the sake of ease.
```
git fetch origin -p
git checkout <branch>
```

For a list of all available branches, you can run:
```
git branch
```

### Example
```
git fetch -p
git checkout Job2
```
----
**If** you want to switch to a branch you have either cloned or checked out before, all you need to do is switch to it, and make a pull to ensure you are up-to-date with the lates changes from remote. This will be the same command above, meaning that git is smart enough to look to the remote repo if you're trying to check out a branch that doesn't already exist locally.

Make sure to run these commands from within the directory in which the repo exists for the sake of ease.
```
git checkout <branch>
git pull
```

### Example
```
git checkout Job1
git pull
```
----
**If** you want to create a new local branch, make sure you are in the repo's directory (in any branch or in master, it doesn't matter). Then run the following command:
```
git checkout -b <new-branchname>
```
This command will make a new branch based on the latest commit at HEAD, which will likely be empty.

### Example
```
git checkout -b Job3
```
----
**If** you want to make a new branch based on another branch that already exists, you can run:
```
git checkout -b <new-branchname> <existing-branchname>
```

### Example
```
git checkout -b Job32 Job1
```