# testing-repo
repo full of nothing for testing git practices

## How to replicate a repo from GA-Enterprise to your personal git

### Get the repo from GA-Enterprise locally
- start with a repo in your personal space on GA-Enterprise
    - that is, `{your name}/{repo name}` and not `DSB-EC-1211/{repo name}`
    - so this is a repo you've already forked or it's one you created in your own namespace
- clone it to your computer ("local")
- navigate into the repo locally and check the location and name of the remote: `git remote -v`, which should show something like this:
```bash
origin	git@git.generalassemb.ly:hc-conklin/testing-repo.git (fetch)
origin	git@git.generalassemb.ly:hc-conklin/testing-repo.git (push)
```
