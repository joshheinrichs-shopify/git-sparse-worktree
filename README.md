# git-sparse-worktree

a prototype that makes it convenient to create sparse worktrees. leverages `git ls-tree` for tab completion so you can interactively select subfolders to clone without checking out the entire repo. 

![](./demo.gif)

## usage

```console
$ # set up zsh completion
$ eval "$(git-sparse-worktree completion)"

$ # clone a repo without checking out its contents
$ git clone --no-checkout https://github.com/torvalds/linux
$ cd linux

$ # create a sparse worktree with just one folder
$ git-sparse-worktree add -b foo Documentation/
$ ls foo/

$ # do the same thing via stdin
$ git ls-tree -r -d --name-only HEAD | fzf --multi | git-sparse-worktree add -b bar
$ ls bar/
```

## todo

* support extending the current worktree
* support repo-configured completions
  * e.g. "any directory containing a README.md"
* make file completions work properly
* bash + fish completion support
* support fuzzy-matching?
* support ephemeral worktrees?
  * e.g. `git-sparse-worktree add --rm`

