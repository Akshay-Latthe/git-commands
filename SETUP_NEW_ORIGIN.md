#  1) SET NEW REMOTE ORIGIN 

### FIRST Remove the remote origin 

"git remote remove origin"

"git remote -v "


### SETUP NEW REMOTE ORIGIN 

steps:

step1:
"git remote add origin https://@github.com/<git_repo_url>"

step2:

"git remote set-url origin https://<accesss_token>@github.com/<git_repo_url>"

check fetch and push origin are setup is done

"git remote -v "

### TRY TO PUSH FILE ON GITHUB TO CHECK THE PERMISSIONS ON MAIN BRANCH 

"touch readme.md "

"git add readme.md"

"git commit -m "readme.md is added"

"git push origin dev"

### CREATE NEW BRANCHES  "dev"

"git branch"

"git chekout -b dev"

"touch xyz.txt"

"git add xyz.txt"

"git commit -m "xyz.txt""

"git push origin dev"


