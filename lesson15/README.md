## Git intro

![intro](./images/image-1.png)
![intro](./images/image-2.png)

## Git Workflow:
![Workflow](./images/image-3.png)

![Git status](./images/image-4.png)

```git add --all```

![git log](./images/image-5.png)

```git push -u origin master```

![git checkout](./images/image-6.png)
![git checkout](./images/image-7.png)

### Delete the branch locally
```git branch -d feature/authentication```

## Git Rebase
![Rebase](./images/image-8.png)
Let's say you and another developer working on a same branch. you add some changes in the branch and commit it locally. Another developer also add some changes in the branch and push those changes in the remote repository. As you  can see in the screenshot, you don't know another developer changes and another don't know your changes as well. When you push your changes to remote, you cannot do that, you will get an error because there are some other changes that have been pushed already to the remote branch.
![Rebase](./images/image-9.png)
First, i need to pull before pushing my changes.
![Reabse](./images/image-10.png)
What happens is that git pull basically pulls the changes locally and creates a new commit.
![Rebase](./images/image-11.png)

Git rebase helps us tp avoid merge commits

```git pull -r```
![Rebase](./images/image-12.png)

## Stop tracking file
![stop](./images/image-13.png)
```git rm -r --cached node_modules```

## git stash
![Stash](./images/image-14.png)
![Stash](./images/image-15.png)
![Stash](./images/image-16.png)