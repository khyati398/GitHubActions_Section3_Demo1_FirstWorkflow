# Getting Started with GitHub Actions

This repository will be used to get started with GitHub Actions!

1. Workflows must be defined under <git-repo>/.github/workflows/<workflow-name>.yml
2. It is defined in yaml file where indentation matters and helps us define parent and child elements 
3. Note that .github folder is defined inside a git repository, that is, inside your project repository. Hence, changes in workflows will always be committed and remain part of your repository. That repository could solely be in GitHub as remote repository or could be as local repository connected to remote repository.

As soon as GitHub notices the path <repo>/.github/workflows/<name>.yml file, It understands it as workflow and triggers based on the event defined in workflow yaml file.

4. You can either create remote repository and create the workflows directly from Github UI under Actions -> New Workflow -> Where you'll find many templates for setting up workflow; depending upon the tool/environment requirement you can select those, here we have selected "simple workflow"

5. Now you can define the workflow and commit in the repo.

6. To run the workflow if "manual_dispatch" is set then go to Action -> Workflows -> Select the workflow and run

7. You can either define workflow as stated above i.e. directly in remote repo using GitHub UI or work on the local repo and then push it to remote repo.

7.1. Create the project directory on local system, create .github/workflows folder and initialized the project directory with git and make it git repository.

7.2. Create empty remote repo or use the existing remote repo as per your requirement and attach it to local repo so that workflows can be pushed to remote repo.

7.2. Define workflows under .github/workflows/ folder and create workflow yaml file.

7.3. Commit the workflow file to local repo and push to remote repo

Steps using 2nd method:

1. git init //Stay in your project directory. Here, it is 01 First Workflow
2. git add readme.md //Create read me file and commit, we need to create first commit to have   branch created
3. git commit -m "created readme file
2. Running git remote add command to attach remote repo to local repo.

 git remote add origin "https://khyati398@github.com/khyati398/GitHubActions-First-Workflow-1.git"
 Syntax: git remote add <remote-alias> <url>

3. Add to staging and Commit the workflow
    git add .\.github\
    git commit -m "First-Workflow-v1"

4. git push -u origin main //Syntax: git push -u <remote-repo-alias-name> <local branch>
    OR
   git push --set-upstream <remote-alias> <local-branch>

   This command associates local branch to remote branch, this is recommended when automatic link is not present between local branch and remote branch, for e.g.: when a new local branch is created which is not present in remote repo and then when you push from that branch to remote repo, git will throw you error saying that current branch has no upstream branch.
   Hence, on running above command, git will create a same name branch on remote and set up the link between that and the local branch. Hence, when the next time you are required to push or pull the changes, you can simply run "git push" OR "git pull" as git knows the relationship.

   To setup link between local branch and existing remote branch, you could use below syntax:
   i. git branch --set-upstream-to=<remote>/<remote-branch> <local-branch>
      OR
   ii. git branch -u <remote>/<remote-branch> <local-branch>

5. Now, go to actions -> workflows in Github UI and run your workflow and check the output by selecting the job in the workflow.

Note: If you're first time pushing files/folders to remote repo then you will be asked you for entering credentials and that could be the password or access token generated against your github username. This is to allow git to connect to remote repo and able to push the files. You need credentials in case of pushing, in case of pulling you don't need it.

[Steps to generate access token: Go to user on github -> Settings -> Developer settings -> Personal access token ] 

You will be asked to enter credentials only the first time then windows will save it in the windows credentials manager. And use it everytime you push the files.

For github to ask you for the password while connecting to remote repo; you need to enter username to remote repo to local repo like below:
git remote add <remote-repo-alias> "https://<username>@<remote-url>" 
E.g.: 
git remote add origin "https://<user-name>@github.com/khyati398/GitHubActions-First-Workflow-1.git" 

If you forget to add username like above in remote url then you will be asked for credentials while pushing the files from local repo to remote repo. You could pass access token or password. In case of password, it stays in the credentials manager until you change your password on github ui and you can check this by searching "windows credentials manager on your system" and under git url, you will be able to see the details. 

Now if you have provided access token with set expiry date then it will get expired after the data and you will be asked to enter password again in case of push action or while connecting remote repo if you have passed username with it.





