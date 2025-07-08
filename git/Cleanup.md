# Remove local branches that have been merged into main
Using git bash or on linux:
```bash
git checkout main
git pull
git branch --merged main | grep -v "main" | xargs git branch -d   # Delete merged remote branches except main
```

# Remove remote branches that have been merged into main
Using git bash or on linux:
```bash
git checkout main
git pull
git fetch --prune                 # Prune deleted remote branches
git branch -r --merged main | grep -v "main" | sed 's/origin\///' | xargs -I {} git push origin --delete {} # Delete merged remote branches except main
```
