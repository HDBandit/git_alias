# git_alias
Git aliases to prepare branches for Pull Request in a easy way.

The objective of these aliases is to clean the commits done in your branch, and squash them in 1 commit in order to maintain 
the historic of your branch elegant and clean.

How it works ?
You have to copy and paste the aliases in the configuration file used by your shell. In my case I am using zsh, and aliases are
configured in your home directory in a file called .aliases.

Once you have the aliases running. You can create a new branch from your master branch using the command:

nb <branch_name>

This creates a new branch, but also add a tag to mark the beginning of your commits in that branch. After that, you can do all
the commits you want.

Once you decide your branch is ready for a pull request. You have the execute the command:

ppr <branch_name> <final message for the commit>

This command performs a reset soft until the tag created with the command nb (all the commits done in your branch), and squash 
all the changes in one commit. After that, it deletes the created tag and performs a rebase with master.

Then you have your branch clean, and organized and ready to be pushed to your remote repository whenever you want.
