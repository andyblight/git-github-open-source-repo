# How To Configure A Repo Like An Open Source Repo

The most difficult part of setting up a new repo is working out the ruleset to apply.  The GitHub documentation is extensive, so it is far easier to ask a Gen AI.  These were the Gemini generated instructions I followed (it took three prompts to get it right!)

## Create a Base Repository

1. Create a public repository on GitHub.
1. Initialize it with a `README` or `.gitignore` file.
1. Establish a default branch named `main`.

## Protect the main branch using a ruleset

To mirror an open-source workflow with your specific settings, configure the rules exactly as follows:

1. Locate Restrict updates. Turn this On. This instantly blocks direct git pushes to main for anyone who does not have explicit bypass permissions.
1. Locate Require a pull request before merging. Turn this On to force all code through the fork-and-PR process.
1. Once enabled, look directly below the pull request setting for a nested option named Required approving reviews. Set this to at least 1.
1. Check the box for Dismiss stale pull request approvals when new commits are pushed to ensure modifications are re-reviewed.
1. Locate Block force pushes. Turn this On to protect the history of your main branch.
1. Locate Require status checks to pass. Turn this On if you use automated tests that must pass before merging. (I don't use this).

Because you want to test the workflow exactly like an open-source contributor, you must remove your own ability to bypass these rules:

1. Scroll to the very top of that same configuration screen.
1. Look for the Bypass list table.
1. If your username or the Repository admins group is listed there, click the trash can or remove button next to it.
1. Click Save changes at the bottom of the screen.

**Note: This was tested on 14 May 2026.  GitHub like to change things so this may not work for you!**
