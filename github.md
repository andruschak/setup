// "#" seems to create a header in github - others?

// would also appear that everything needs to be double spaced for newline by default


# Git flow
workingdir--> index (stage)--> head (commit)

# General git commands
git remote -v

git log

git branch -av

git status

#Configure machine settings:
git config --global user.name "name"

git config --global user.email "user@mail.com"

If you have 2FA enabled, you need to generate a "Personal Access Token" to use as a push password! Burned me for a while while experimenting with multiple machines.

# Snag existing
git clone username@host:/path/to/repository


# Setup new
git init

git add <filename> OR git add *

git commit -m "commit message"

git push origin master // finally send to github


# If you started on your own without cloning first
git remote add origin <server>


# Branching
git checkout -b new_feature // add new branch

git push origin <branch> // push so others can see on github

git branch -d new_feature // remove branch


# Switch branches
git checkout master


# Start fresh! 
git fetch origin

git reset --hard origin/master // dumps everything local and redownloads



# References:
Git basic commands (no deep shit - http://rogerdudler.github.io/git-guide/):

