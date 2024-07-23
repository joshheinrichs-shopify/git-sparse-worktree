# git-sparse-worktree

a prototype that makes it convenient to create sparse worktrees. leverages `git ls-tree` for tab completion so you can interactively select subfolders to clone without checking out the entire repo. 

![](./demo.gif)

## usage

```console
$ eval "$(git-sparse-worktree completion)"
$ git clone --no-checkout https://github.com/torvalds/linux
$ cd linux
$ git-sparse-worktree add -b docs Documentation/
$ cd docs
```

## todo

* support passing paths in from stdin
  * e.g. `git ls-tree -r -d --name-only HEAD | fzf --multi | git-sparse-worktree add`
* support repo-configured completions 
  * e.g. "any directory containing a README.md"
* make file completions work properly
* bash + fish completion support
* support fuzzy-matching?
* support ephemeral worktrees?
  * e.g. `git-sparse-worktree add --rm`

