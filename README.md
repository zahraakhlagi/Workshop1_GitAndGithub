## Workshop about Git&Github

### Initialize a Git
```bash
# Tell git to start watching this folder
git init
````
**Note** git init create a hidden `.git` folder inside the project , all setting and history of the repository stores in this folder

### Create  files
```bash
echo Hello Git > index.html
echo body { color:blue;} > style.css
````
### Stage and commit
```bash
git status
# check the status (now is red)
git add .
# add files to the stage area
git commit -m " comment"
# save them permanently
```

### Update and commit again
change `index.html`
```bash
# Modify index.html
echo Hello Git updated! > index.html

git diff
# see the difference
git add .
git commit -m ""
#stage and commit the update
```
### Using restore
```bash
echo THIS IS A MISTAKE > style.css
git status
# lets get the old version back from the last commit
git restore style.css
```

### Fixing a mistake in the staging area

```bash
# add some garbage to style.css and stage it

echo "body{color:PINK;} ">> style.css

git add style.css

# its a green (staged)
git status

# lets unstage
git restore --staged style.css

# now its back to being red (unstaged)
git status
# Discard the changes completely
git restore style.css
```

### Review your progress and understanding Logs

```bash
git log --oneline

```
### Traveling back in time (Reverting to a Hash)
```bash
# to visit a previous version (read only mode):
git checkout <commit-hash-id>
# back to the main
git checkout main

#move your project back to the old hash permanently (it delete all commit and changes after this version)
git reset --hard <commit-hash-id>
```
### option B: The restore and move forward ( safar)
```bash
# keep your history moving forward, this is much safar!
git log --oneline
git restore --source=<commit-hash-id>
git status
git add 
git commit -m "Restore project to version <hash-id>"
git log --oneline
```













