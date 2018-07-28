# hello-world
TClone repository
Open your terminal and navigate to folder where you want to clone in the repository
git clone <repository-link> # Clone repository using repository link ending with .git
cd <reporitory-name> # Move to directory created with cloning
0. Pre-flight check
Fetch latest state of remote/origin repository with git fetch --all --prune
Make sure you are currently in branch that you want to create new branch from by checking out (this is usually default repo branch, mostly master) with git checkout <branch_name>
Make sure your current branch is in it's latest state with git pull
1. Create new branch
First you need to create new branch and checkout to it

git branch <new_branch_name> # Create new branch
git checkout <new_branch_name> # Checkout new branch
2. Publish new branch
Then publish your branch to remote and set upstream i.e.make local branch 'follow' remote one

git push origin $(current_branch) # Push current branch to origin
git branch --set-upstream-to=origin/$(current_branch) # Set upstream
Setting upstream to corresponding origin branch allows us to just use push and pull later on without specifying to/form which origin branch are we pushing/pulling

3. Make and push new commits
Now edit the code, make changes and additions and commit them using

git add <file_name> # Stage file
# You can use 'git add --all' or 'gaa' to stage all modified files
git commit # Commit changes
# After this, editor will open so you can enter commit message
# Always prefer this rather then 'git commit -m <commit_msg>'
git push # Push commit to origin
# This is now possible without arguments because we've set up upstream in step 2
4. Open pull request on GitHub
After you've made all changes and additions you wanted you can go to GitHub (or any other service your origin is hosted on) and open new pull request with current branch as head branch and branch you branched from in step 1. as base branch.

5. Wait for review and/or merge PR (pull request)
Now, if you are in team or have a lead on project you can wait for them to review PR and merge it or if you work alone on the project you can review your own changes to double check for errors and merge it yourself.

If you aren't alone on the project or you don't own it, good practice is to never merge your own PR but to wait for lead or some of your peers

5.1 Delete branch
You can now delete branch if you no longer intend to work on it.

Delete it on GitHub i.e. origin
Delete it locally using git branch -d <branch_name>
6. Chose new task/feature and repeat
Select yourself new task/feature and repeat from 0.
