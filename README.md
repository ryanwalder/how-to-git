# how-to-git

A repo with some branches and some pull requests designed to show how to:

* Make good commits
    * Not too much sausage (squash commits)
    * Not too little sausage (splitt commits)
* Make good Pull Requests
* Review Pull Requests like a boss
* Use the Fetch & Rebase method of working (rather than pull)

Designed to be used in conjunction with my [How to git](https://docs.google.com/presentation/d/1_990RTb0fWJnp_0Z6sSUvCOn_dR2k2Ko5QEju753en4/edit?usp=sharing) slides.

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
