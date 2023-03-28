# Intermediate Git Commands exercises
These are a few git commands that go beyond the bare basics but I use very frequently

For these exercises you can use the repo we have used on day 1:
`git clone https://github.com/twbraam/git_workshop.git`

## git reset
### git reset --hard
Throw away everything that you did since your last commit

1. Open Git Bash and go into your repo directory
2. Make changes to `newfile.txt`
3. Delete `webpage.html`
4. Look at the changes that you made: `git status`, what do you expect to see?
4. `git reset --hard`
5. Your files should be reverted to the state of step 1.

### git reset <commit hash> --hard
Go back to an earlier commit, throwing away any commits made after that.
DANGER: Your commits will be deleted, never push this to a remote branch
        unless you are 100% sure that nobody is using that.

1. Use an IDE to take a good look at the commits that were made in the past.
   If your IDE is not working well, use the following command. It should look
   like a graph as shown many times in the class:
   `git log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(auto)%d%C(reset)' --all`
2. Whatever branch you are, try to find an earlier commit on that branch. If you are on main, they
   are all listed on the left-hand side. Copy that commit hash.
3. `git reset <commit hash> --hard`
4. Run the same command from step 1.
5. Your current state should now be at the hash that you selected. Moreover, all the commits
   from after that commit should be deleted!

## git rebase
If you find out that `main` (or any other branch that you have branched off of) has new commits
while you were working on another branch and you want to get these commits into your branch as well.

1. Make sure you work with a clean repository.
   If in the last assignment you threw away some commits, just delete the whole directory
   and run `git clone https://github.com/twbraam/git_workshop.git` again to start over.
2. Create a new branch called `feature1`, and checkout
3. Add some commits
4. Now, checkout main and add commits to this branch as well.
   WARNING: Make sure your commits would not cause a merge conflict, otherwise things will get
   pretty advanced.
6. To get the commits from `main` into `feature1`, you need to checkout `feature1`
7. `git rebase main`
8. Behind the scenes, this will create a new branch from the current `main` with those extra commits
   and then add your commits from `feature1` on top. Now you have the latest commits in your `feature1`
   branch as well!
9. Try to run the big `git log` command that was posted in the previous exercise and see what happened

## git cherry-pick <commit hash>
Copy a SINGLE commit from any other branch into your current branch. I use this all the time if one of my branches that I want to throw away has a specific commit that I am interested in.

1. Create a new branch and checkout
2. Add a few commits
3. `git checkout main`
4. Create another branch and checkout
5. Add more commits
   WARNING: Make sure your commits would not cause a merge conflict
6. With all the changes you made in both branches, the files in both should look very different
7. You are currently still in the branch created in step 4. Run `git log` and look for a commit
   from the branch in step 1.
8. Run `git cherry-pick <commit hash>` with the commit from step 7.
9. Use `git log` to see what happened, note that the new commit has a different hash than the one you
   just cherry-picked. That means that we actually created a totally new commit, rather than
   referencing or "merging" the other commit.
