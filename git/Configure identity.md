# Set default identity for all repositories
```
git config --global user.name "Your Name"
git config --global user.email "your-email@gmail.com"
```

# Set identity for an individual repository
After cloning or initializing a repo, run these commands inside the repo folder:
```
git config user.name "Your Name"
git config user.email "your-email@gmail.com"
```

# Set identity for all repo's in a specific directory
Note that on windows the pathing in gitdir needs to be in windows format, so instead of `/c/ExampleDir/` use `C:/ExampleDir/` 
```
git config --global includeIf.gitdir:~/path/to/personal/folder/.path ~/.gitconfigToUse
```
