// "#" seems to create a header in github - others? maybe html

// would also appear that everything needs to be double spaced for newline by default

// always remember to do a "pull" when you pick up from any machine so you always have the latest

# get me up and running

ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

eval $(ssh-agent -s)

ssh-add ~/.ssh/id_rsa

cat ~/.ssh/id_rsa.pub

paste public key into the SSH keys section of your github settings

switch to SSH (can check with "git remote -v"

git remote set-url origin git@github.com:USERNAME/REPOSITORY.git






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

If you have 2FA enabled, you need to generate a "Personal Access Token" to use as a push password! Burned me for a while while experimenting with https on multiple machines

# SSH-keys (use the ssh-agent for additional security)
open git bash (if windows)

ssh-keygen -t rsa -b 4096 -C "email@address.com"

Enter a file in which to save the key (/c/Users/username/.ssh/id_rsa): <press enter>



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

Git ssh basics (https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)

Github ssh w/ agent (https://help.github.com/articles/working-with-ssh-key-passphrases/)


