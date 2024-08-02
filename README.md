# Feature branches
- Feature branches are the workflow, step by step process for using Git and Github. 
1. Create a feature branch (new branch)
2. Upload feature branch to Github
3. Create a pull request (Do code reviews by other SE)
4. Merge feature branch into master branch(Merging happens on github)

- In order to implement this:
Create a new branch `git branch new-feature`.
- Switch to the feature branch we just created `git checkout new-feature`.
- Create a file named `new-feature.js`.
- Follow the procedure `git add .`, `git commit -m “new-feature"`.
- Push it to Github repository: Go to Github and create a new repository.
- Now we need to upload our master branch first, because master branch is the default branch, and usually at work the master branch would have already been pushed to github, but since we initialize the git repository on the local repository, and did not initialize it on the remote repository (github), we need to switch to the master branch and push it to github, and then we need to switch to the feature branch and push it to remote repository (github) so that it is consistent with what we're working on. 
- So first, switch to master branch: `git checkout master`.
- In our local repository we need to add a link to the Github repository. `git remote add origin url`
- Then, push the master branch to github: `git push origin master`, now the master branch can be seen in github repository.
- Switch back to the feature branch: `git checkout new-feature`.
- Push it to github: `git push origin new-feature`
Now we need to create pull request, pull request takes the feature branch and compares it to master branch and initiates code review, let other people see the code and changes, let them comment on your code.
- Click on `Pull requests` tab on github, click on `New pull request`. Here we have `base: master` and `compare: master`.
- Change the `base: master` to `compare: new-feature`, then click on `Create pull request`. This initiates the code review, we can give url to the teammates, and they can see the changes, if there is any issue with the changes, they would comment on it. 
- Teammates would click on `Files changed` section, if there is any issue, they can leave comments. 
- Once the comments are resolved and issues and bugs are fixed, we need to merge the feature branch to the main branch. For this click on `Merge pull request` and then `Confirm merge`. 
Since we merged the feature branch to the master branch on github, we need to sync those changes back to the local repository. 
- The HEAD points to the `new-feature` branch, we need to change that to `master` branch, because we want to pull the changes from the master branch in github back to the master branch in the local repository, for this we use this command `git checkout master`.
First we use this command `git fetch` which fetches the changes from the github repository, then we use this command `git log --all --graph` to see the changes on Github repository and also see the local repository.
-  Now we can see that the remote master branch is ahead of the local master branch, we need to update the local master branch so that the local branch will be in sync with the remote master branch. For this we use this command: `git pull origin master`
- With this command: `git log --all --graph`, we can see that the local master branch is in sync with what is on github. 
