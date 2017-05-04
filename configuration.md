# GIT Configuration

## gitconfig

content of `~/.gitconfig`:
```
[user]
  name = mstovicek
  email = primary@example.tld
[core]
  # windows->true, linux-> input
  autocrlf = input
  safecrlf = false
  # do not commit file mode permission
  filemode = false
[push]
  default = upstream

```

## hooks

## aliases

```
[alias]
  f = fetch
  # updates your branch with upstream (if fast-forward is possible)
  ff = !git merge --ff-only `git rev-parse --symbolic-full-name --abbrev-ref=strict HEAD@{u}`
  fp = fetch --prune
  st = status
  cm = commit -m
  br = branch
  co = checkout
  cp = cherry-pick
  df = diff
  dfs = diff --staged
  rb = rebase
  rbi = rebase -i
  rbc = rebase --continue
  rba = rebase --abort
  rh = reset --hard
  # graph for current branch
  l  = log --graph --decorate --pretty=oneline --abbrev-commit
  # graph for all branches
  ll = log --graph --decorate --pretty=oneline --abbrev-commit --all
  # log for current branch showing diffs (-m is for showing mergecommits too)
  ld = log -p -m
  # log for current branch showing summary of changed files (-m is for showing mergecommits too)
  ls = log --stat -m
  # remove remote branch (remote must be named origin), usage: git rmb test
  rmb = !sh -c 'git push origin :$1' -
  # shows local > tracked remote
  brt = for-each-ref --format=\"%(refname:short) > %(upstream:short)\" refs/heads
  # commit all changes to a work-in-progress commit
  wip = !git add $(git rev-parse --show-toplevel) && git commit -m WIP --no-verify
  # push current branch
  pb = !git push -u origin `git rev-parse --abbrev-ref HEAD`
  # force push current branch
  pbf = !git push -f -u origin `git rev-parse --abbrev-ref HEAD`
```

## colours

```
[color]
  ui = auto
[color "branch"]
  current = yellow reverse
  local = yellow
  remote = green
[color "diff"]
  meta = yellow bold
  frag = magenta bold
  old = red bold
  new = green bold
[color "status"]
  added = green
  changed = yellow
  untracked = cyan
```

