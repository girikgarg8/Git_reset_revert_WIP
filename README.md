## Undoing changes in git

If we made some errors during creating the commits, and we want to undo the commits, we have several options available with us like `git checkout`, `git reset` and `git revert`. Let's explore them:

1. `git checkout <commit ID>`: Already discussed in detail, in earlier tutorials. Using this command, moves the HEAD pointer to the specified commit (resulting in an detached HEAD state), but doesn't move the branch pointer.

2. `git reset`: The primary difference between `git checkout` and `git reset` is that the `git reset` command moves the branch pointer to the specified commit (and consequently, the HEAD pointer too). `git reset` comes with three options `--soft, --hard and --mixed`. The `--soft` option is considered to be safe, `--hard and --mixed` options should be used with caution.

Let's understand these options:

1. `--soft option`: This option is used to reset the branch pointer (let's suppose master for the purpose of discussion) to the specified commit. The changes in the staging area and the working area from the current commit are not cleared, that's why it's considered to be safe. 

An important question that comes up, is that how do we go back to the original commit: let's say we reset to commit 3 from commit 4, is there a way we can make the master branch point to commit 4 again? 

There are two ways to do this:

1. Using `tag` for commit 4 before using the `git reset` command, so that we have a reference to the commit using the tag.

2. Using `git reset ORIG_HEAD`. The ORIG_HEAD is a backup reference to the HEAD before a drastic change is made to the HEAD pointer. In other words, we can also say that the ORIG_HEAD points to the branch before the `git reset` option is executed.

Unrelated but a useful piece of information: Using the `git --no-pager log ` command can be used to disable the pager while viewing the commit history.

![Git_reset_soft_demo](Git_reset_soft_demo.png)

The changes in the staging area and working area are preserved when using soft reset:

![]()