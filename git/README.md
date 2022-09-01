# Git Knowledge Base

### List git configuration (including username and email)
```git config --list```

### Set git username and email
```
git config --global user.name "Satoshi Nakamoto"
git config --global user.email "satoshi@bitocin.com"
```

### Add content (files, directories) to staged state
```git add .``` 

### View differences between cache/stage (not yet commited) and HEAD (commited)
```git diff --cached```

### Create new commit of a staged content 
```git commit -m 'Initial implementation of feature A```

### Show difference between unstaged and staged
```git diff```

### Show difference between current state and last commit
```git diff HEAD```

### Show difference between two latest commits 
```git diff HEAD^```

### Show git log of commits
```git log```

### Update latest commit
```git commit --amend```

### Set remote repo origin location
```git remote add origin https://github.com/origin-account/origin-repo.git```

### Push all branches to the origin
```git push origin```

### Push master branch to the origin
```git push origin master```