# how-to-git

A repo with some branches and some pull requests designed to show how to:

* Make good commits
    * Not too much sausage (squash commits)
    * Not too little sausage (split commits)
* Make good Pull Requests
* Review Pull Requests like a boss
* Use the Fetch & Rebase method of working (rather than pull)

## Notes

Obviously some of this is very opinionated. I am working to the following principles when making this guide:

### Good commit messages

[This post](https://chris.beams.io/posts/git-commit/) by [Chris Beams](https://github.com/cbeams) delves deep into what makes a good commit message and why.

### Good commits

We don't need to see how the sausage is made. A good commit should be the code needed for a single logical change. Nothing more, nothing less.

### Making pull requests

Much like the Good commits section above good Pull Requests make everyone's lives easier.

## Handy git settings

These are setting which improve over the base setup

### Always fast forward merge

As discussed in the slides, merge commits are ugly but that doesn't mean we can't still use the `merge` functionality of git.

By default merge will try and [fast-forward](https://sandofsky.com/images/fast_forward.pdf) commits without creating a merge commit if possible but will create a merge commit if needed.

With this setting it means it'll throw an error rather create the merge commit which give you the chance to fix the thing causing the merge commit before it happens, keeping you log nice and clean.


```
$ git config --global merge.ff only
```

## Git aliases

Tired of typing so much? Make aliases!

Run the below commands to add the aliases to your global config, once entered you can then use the word after the `alias.` as if it were a git command itself

EG:

```
$ git config --global alias.st status
```

And `git status` becomes `git st`

### Shorthand

```
$ git config --global alias.f fetch --all
$ git config --global alias.co checkout
$ git config --global alias.br branch
$ git config --global alias.st status
$ git config --global alias.cp cherry-pick
```

### Time Savers

#### Uncommit

Sometime you just want to get rid of the last commit but keep the changed files.

```
$ git config --global alias.uncommit 'reset HEAD~'
```

#### Unadd

Accidentally added a file to the staging area which you didn't mean to?

Use `git unadd filename` to remove a single file or `git unadd` to unadd everything.

```
$ git config --global alias.unadd 'reset HEAD'
```

#### Fancy log

```
$ git config --global alias.lg 'log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit'
```

#### Log with GPG signatures

Using GPG signed commit? (You should be!) And want to check the signatures on commits?

```
$ git config --global alias.pulls 'pull --show-signatures'
```
