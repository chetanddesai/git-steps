## Code Contributions

### Local Setup

Make sure git knows your real name and email address:

```text
$ git config --global user.name "Jon Doe"
$ git config --global user.email "jon.doe@example.com"
```

### Step 1: Fork and Clone

From the GitHub UI, fork the project into your user space or another organization.  Following the steps below, clone locally and add the upstream remote.

```text
$ git clone git@github.com:username/project.git
$ cd <project>

## If you have SSH keys set up, then add the SSH URL as an upstream.
$ git remote add upstream git://github.com/<organization>/project.git

## If you want to type in your password when fetching from upstream, then add the HTTPS URL as an upstream.
$ git remote add upstream https://username@github.com/<organization>/project.git
```

If later you want to switch your remote upstream from `https` to `ssh` or vice versa you can edit it using the [`git remote set-url`](https://help.github.com/articles/changing-a-remote-s-url/) command.

### Step 2: Commit

Writing good commit logs is important.  A commit log should describe what
changed and why.

### Step 3: Rebase

Use `git rebase` (not `git merge`) to sync your work from time to time.

```text
$ git fetch upstream
$ git rebase upstream/master
```

### Step 4: Test

Bug fixes and features **should come with tests** and coverage should be above 80%

```text
$ mvn clean test
```

Make sure that all tests pass.  Please, do not submit patches that fail this check.

### Step 5: Push

```text
$ git push origin my-feature-branch
```

Go to https://github.com/yourusername/project and select your fork.
Click the 'Pull Request' button and fill out the form.

Pull requests are usually reviewed within a few days.  If there are comments
to address, apply your changes in a separate commit and push that to your
feature branch.  Post a comment in the pull request afterwards; GitHub does
not send out notifications when you add commits.
