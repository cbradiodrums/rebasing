# Rebasing

- The following is a guided project that will help you understand the git rebase command..

## Description

- Throughout your Lambda School experience thus far you have learned how to work with Git and have had practice using the basic commands for staging, commiting, and pushing (publishing) your commits to a repo. Learning now, the rest of what you need in order to work as a productive member of a product organization will set you up for success not only in labs, but give you insight into what how the product teams work in the real world.

## Purpose

- Knowing how to use the git rebase command is absolutely vital for you to succeed as a tech professional. That is the purpose of this exercise.

## Objectives

- By the end of this guided project you will have demonstrated the following:
  - You will be able to create a _branch_ off of the **main** branch of a repository.
  - You will be able to _rebase_ the **main** branch onto your feature branch.

## Instructions

The following is a list of steps and instructions on how to complete this guided project.

- **Step 1️⃣:** Fork this repo into your personal account
  - then clone this repository by clicking the green **Clone or Download** (or new **Code**) button in the top right.
![Clone/Download](https://tk-assets.lambdaschool.com/054e5ad4-75cd-4b98-b929-7bf453bc8263_ScreenShot2020-04-13at7.31.05AM.png)

- **Step 2️⃣:** CD into the repository and create a branch off of the main branch.
  - `cd rebasing`
  - Name the branch **"feature/add-my-name"** `git checkout -b feature/add-name`
  - **note**: this is a common naming convention. In labs you will often use the Jira issue number in your branch name.
  - Once the branch is created, you've been switched to the new branch.

- **Step 3️⃣:** Now that you have created your branch you're ready to do your work. Our task for the day is to have you add your name (`### Your name`) heading to the end of this README.md file.
  - (**note** the semantically chosen branch name you created coincides with the task at hand)

- **Step 4️⃣:** Run your typical staging and commit:
  - `git status` - should only show the one file as modified
  - `git add <file-name>` - try to practice only adding files that support your commit message
  - `git commit -m 'your message'`
  - 💥**note:** you're committing to your branch NOT to the main branch. (!!VERY IMPORTANT!!)💥

- **Step 5️⃣:** Now lets make some changes on the main branch that represent the work from another developer. We will rebase these commits into our feature branch.
  - `git checkout main`, `git pull` will put us on the main branch and update it
  - Now lets add `### Space Ghost` to the end of this README.md file ABOVE/BEFORE the header `### Blip`.
  - Once again, stage and commit this change
  - `git status` , `git add README.md` , `git commit -m 'your message'` , `git push`.
  - **note** this is a fork so you will be able to push to the main branch, typically this will not be allowed in production repos.
  - Lets repeat this process adding a commit for each name. Add the following names BEFORE `### Space Ghost`
    - Zorak
    - Brak
  
- **Step 6️⃣:** Ok, we now have 3 commits on the main branch that our feature branch doesn't have.
  - Open the log of commits `git log` and look at the last 4 commits. The first 3 are the new ones you just created, the 4th one is the commit you created your feature branch from. 
  - Now lets switch to the feature branch `git checkout feature/add-my-name`
  - Open the log of commits `git log`. Do you see the 2nd commit that is the same as the 4th one on the main branch?

- **Step 7️⃣** Let's rebase those 3 new commits on the main branch to our feature branch
  - `git rebase main`
  - You should see the message `Successfully rebased and updated refs/heads/feature/add-my-name.`
  - Now have a look at the log of commits `git log`
  - You should see your name commit as the first entry. You should also now see the 3 new commits from main following your commit.

### Space Ghost

### Blip (add 3 names above this line 👆)
