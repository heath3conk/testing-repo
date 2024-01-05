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

### Create a repo with the same name on your personal git
- ideally, make the new repo without any README or .gitignore file to reduce any issues about merging
- I created mine with just the MIT license, which is a file that didn't exist in my GA-Enterprise repo

### Add your personal git repo as a second remote locally
- on your computer, use the `git remote add` command to connect your local version of the repo to your personal git account
- that command takes two arguments: 
    - a label you'll use when you push or pull from the remote; in this example, my GA repo is labelled "origin" so I'm going to label this one "personal"
    - the URL or SSH link to your repo 
- I used the label `personal` for mine so my add looked like this: `git remote add personal git@github.com:heath3conk/testing-repo.git`
- check your list of remote links again with `git remote -v`:
```bash
origin	git@git.generalassemb.ly:hc-conklin/testing-repo.git (fetch)
origin	git@git.generalassemb.ly:hc-conklin/testing-repo.git (push)
personal	git@github.com:heath3conk/testing-repo.git (fetch)
personal	git@github.com:heath3conk/testing-repo.git (push)
```

### Sync your local repo to your new personal repo
- run `git pull` against your personal repo, providing both the label you gave it and the name of the primary branch in your repo: `git pull personal main`
- if you get an error or warning about reconciling divergent branches, you can run that with the rebase flag as `git pull -r personal main`
- now my local repo has the MIT "LICENSE" file that was generated when I created the repo on my personal git account, plus everything that was already in it.
- Note: The license is not required, it's not a bad thing to have in any public repos on your personal account but it's not necessary. Mostly I wanted to make sure I could integrate files from two different remotes without any problems

### Push your local repo to your personal repo
- as with your `pull` you'll need to specify which remote & branch you want to push changes to: `git push personal main`
