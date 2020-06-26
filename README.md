A tutorial for understanding different merging methods.

# Explicit Merge

checkout the develop branch:
```
git checkout develop
```

Because we want to do an explicit merge and there have been no changes to the develop
branch since the `feature/explicit-merge` branch was created, use the ``--no-ff` flag so
that the merge is not done with fast forward, but will create a merge commit.

Do an explicit merge of the feature/explicit-merge branch:

```
git merge feature/explicit-merge --no-ff
```

You may edit the merge commit statement in your editor or simply close it to accept the
default statement.

# Implicit Merge (Rebase and Fast Forward)

We are going to do a rebase merge, which is really doing a rebase and then a merge with 
fast forward.

```
git checkout feature/rebase-merge
git rebase develop
git checkout develop
git merge feature/rebase-merge
```

# Squash Merge

We should still be on the develop branch. We are going to merge the `feature/squash-merge` 
branch by doing a merge with the `--squash` option, which will merge all of the changes
from the  `feature/squash-merge` branch.

```
git merge feature/squash-merge --squash
```

We then need to commit the changes.

```
git commit
```

By not including the `-m` with your commit command, you will be able to modify a draft
commit message containing every message from your squashed commits before finalizing your
commit.

# Interactive Rebase

This is where I personally prefer to use a tool such as SourceTree to be able to better
see what changes I'm making. You can do this purely from the command line, but be careful
as you can introduce merge conflicts if you put commits in an order that git can't process.
You can always run `git rebase --abort` to restore if you do get into trouble.

```
git checkout feature/rebase-i
git rebase -i SHA
```

You will need to enter the SHA of the parent commit of the first commit in your rebase.

# Cherry Picking

Cherry picking is where you want to selectively include commits from one branch into your
current branch. They be merged immediate with the original commit messages in place or the
changes can be left uncommitted until committed later with a new commit message.

```
git checkout develop
git cherry-pick SHA
```

You will need to enter the SHA of the commit you want to cherry pick.

You can also use the `--no-commit` flag to add the changes without the original commit 
message or the `--edit` flag to allow you to edit the commit message before your commit is
made.
