# Git & GitHub Open Source Repo

The aim of this repo is for participants to understand how to contribute to an open source project.

I have also included instructions on [how to configure the repo to behave like an open source repo.](configuring-the-repo.md) if you want to read them later.

## Instructions

1. Fork this repo to your personal user account.  See [GitHub instructions](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo).
1. Clone the forked repo onto your PC.
1. Take a look at the files in this repo.  You'll notice the file [`CONTRIBUTING.md`](CONTRIBUTING.md).  Take a look at the contents to see what a real open source project might require of you.
1. Just to see what happens when you forget to branch, make a change to the `fix-me.md` file, commit it and try pushing that to the server.  You should see an error message.  There are two ways to fix this.

    1. First, see if the change is big or small by doing a `git diff` on this revision and the previous revision.

        ```bash
        # Diff this and the previous revision, HEAD~1.
        git diff HEAD~1
        # Alternatively, diff against the remote main branch.
        git diff origin/main
        ```

    1. The change is big, so you want to keep the change:

        ```bash
        # Check the log
        git log
        # Associate the current commit with a new branch so it not lost.
        git branch <my_branch_name>
        # Check the log.  Notice the branches that this commit is attached to.
        git log
        # As we are on the main branch, we need to reset it to the previous commit.
        git reset --hard HEAD~1
        # Check the log. Notice that you can't see the new branch any more and the main branch has reverted.
        git log
        # Check the status.  The repo is clean again.
        git status
        ```

    1. If the change is just a couple of characters, it is often quicker to just delete the change and start again on a branch. To delete that change:

        ```bash
        # Check the log
        git log
        # Reset the branch to the previous commit.
        git reset --hard HEAD~1
        # Check the log. Notice that the previous commit has vanished,
        git log
        # Check the status.  The repo is clean again.
        git status
        ```

1. Create a new branch (or switch to the the one from above if you created it).
1. Fix the deliberate typos in `fix-me.md`.
1. Commit the changes.
1. Add some more text to the and add a couple of lines of text.
1. Commit the changes.
1. Push the branch to your repo.
1. Go to the repo on GitHub and submit a pull request.
1. The maintainer of the open source repo  (Andy) will review your changes, ask you to fix some things, or, if there is nothing wrong, they will merge it to the default branch.

## Acknowledgements

© 2026, University of Leeds.

The author, A. Blight, has asserted his moral rights.
