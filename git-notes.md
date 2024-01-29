1) Add the file to version contol system GIT REPO

"git add FILE1.TXT"

2) Git status of stageing 
"git status"

3) To remove form stageing state
"git rm --cached FILE1.TXT"

**Delete/Remove the file form the folder	

4) Recover the deleted file form stageing 
"git restore FILE1.TXT"

5) commit the file form stageing to version control
"git commit -m "first commit""

deleted file is restored on in same file 

6) logs or histry of commites will be stored 
"git log"
"git log --oneline"
"git lof --oneline --pretty"

7) configration to do 
"git config --global user.name "<>""
"git config --global user.email "<>""

8) brnching for new branch 
**form master/main branch create new branch
"git checkout -b dev"

**check branches present in account 
"git branch "

9)switch to master
"git branch -M main"

10) check branches 
"git branch"

11) clone to repo form git 
"git clone "https://github.com ....""

12) git origin for URL
"git remote -v"

13) pull  all chages made in git repo dirctly in gir repo to lcoal 
"git pull origin main"

VIMP QUESTION FOR INTERVIEW
***"git pull" is pull all chages made on sigle branch 
where 
***while git fetch will take all chages made on all branches of git repo


14) setting git repo privet repo for push permission 
 
reta token / take token for permision to push the local files to remote repo

VIMP for you dont have account detailes of repo and you want to push the code in real time senario you have aks for token for  premission for pssing the code and allwes push code on creating your wone branch and the push over it.
"DONT PUSH YOUR CODE ON MASTER/MAIN BRANCH" 

"git remote set-url --add origin <new_url>"

"git remote set-url --delete origin <old_url>"

