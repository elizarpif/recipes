…or create a new repository on the command line

```shell script
echo "# test" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M develop
git remote add origin https://github.com/elizarpif/test.git
git push -u origin develop

```

…or push an existing repository from the command line
```shell script
git remote add origin https://github.com/elizarpif/test.git
git branch -M develop
git push -u origin develop
```
