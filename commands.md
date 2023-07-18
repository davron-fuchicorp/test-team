i
## terminology

`local (repo)` - this is your copy of the GH repo in you local computer
`remote (repo)` - it refers to repository you GH account.

## How to get access to private pepository

```
to get access to you company's GitHub you need to:
- create public ssh key in you local computer (see create ssh key)
- ask you team how you can add your public key to company GitHub (GH) account.
    if you have enough access to the account you can add it youself:
    - open company GH > go to Settings > SSH and GPG keys
    - click on `new ssh key`:
        - add title
        - paste you public key
```

once you done with ssh keys now you can clone any repo you need

## Clone a repo to your locol

- go to GH, select repo you need, click on `<> Code`, select SSH and copy repo url.
- go to you local terminal (gitbash in Windows) and run <br>
`"git clone <repo url>"`

## Working with GitHub in your local

in you local got to github repo you cloned:

`cd <git repo>`

open file you need to work and start working on it. once you done with it, you need to push you changes to remote repo.

#add changes: <br>
`git add <path/file>` or  `git add --all`

#commit changes <br>
`git commit -m 'you commnets'`
#push changes to remote. this will add all of your local changes to remote.

`git push`
sometime when you are working thi repo first time git wants you to run this command: <br>
`git remote add origin <remote repository URL>`

## create new branch
when you add new feature or fix a bug you need to create your feature branch:

before creation of new branch pull from remote
<br> `git pull`
<br> this will get all new change from remote that were pulled by your team. this will make sure you are creating new branch from updated branch.
#create new branch <br>
`git checkout -b <feature/banch>`
this command take you to this new banch

now you can start working on your task here, once you done. now you can push the changes to remote.

## create pull request (PR) and merge

in GH UI go to `Pull requests` find your changes and select reviewers and click on create new request. make sure you select right repos to and from.
once your changes are approved click or `merge`

### doing locall merge
sometime you done need to create PR to add your chagnes to another branch. in this case you can merge your changes manually.
suppose we have 2 branchs Branch-A and Branch-B
Branch-B is feature branch and you want to add you changes to Branch-A.
<br>in feature branch:

#check your branch

`git branch` this will show in what branch you are.

now change branch to the branch to which you want to add your feature branch chagnes (basically you want to add B branch changes to A branch).
<br>`git checkout Branch-A`

#run merge <br>
`git merge Branch-B`
this will all of your changes to Branch A.

## how to undo your changes
git reset -hard

The git reset –hard command will revert uncommitted changes that exist in files that have been added to the index, whether those files are newly created files, or files that were added to the index in the past and have been edited since the last commit. However, if any new files have been created in the Git repository that have never been added to the index, these files will remain in the project folder after the hard reset.

## cancel last commit:

`git reset HEAD^` 

this will only undo changes. all files and changes will remain.

to remove all completely and return to previous commit:

`git reset --hard HEAD^`

It's important to note that git reset HEAD^ only undoes the commit itself and moves the branch pointer. It does not modify the files in the working directory. If you want to discard the changes completely, you can use git reset --hard HEAD^. However, be cautious as this command will discard the changes permanently without the ability to recover them.
