## Introduction to Open Source with Github

## Introduction

Open source software has been around for decades, but it's only recently that the term "open source" has come to be recognized as a buzzword. The idea behind open source is simple: It allows users to modify a piece of code without asking for permission or paying for it. In this guide, we'll show you how easy it is to contribute to an open-source project on Github and why that matters.

![docs.webp](https://cdn.hashnode.com/res/hashnode/image/upload/v1664793340423/VMga1Ylks.webp align="left")

GitHub is a web-based hosting service for version control using Git. The site hosts software development projects that are built by individuals or companies who use it as an online collaborative platform to share code and manage projects collaboratively



## Why Open Source?

Open source is a way of sharing knowledge with the world. Some people contribute because they want to help others, some do it for their own learning, and others do it because they're passionate about the project itself.

## Different types of Contribution roles in Open Source

![contributor.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664793078925/FrWNzLl2Q.png align="left")

>Contributions range from documentation to development, testing and design.

### Documentation:
 Contributors are encouraged to submit articles on open-source projects that they are working on or have experience with. This can be as simple as adding new sections in existing documents or writing a completely new one.

### Development: 
Contributors can contribute code by improving existing features of the project or creating entirely new ones. Some open source projects have strict rules about how you can use the code that they release; others don't care if someone uses their code for their own purposes, so long as they keep giving back when asked! The latter type tends to attract more contributors because it gives them an opportunity to see firsthand what goes into building something like this up from scratch (which is usually much harder than people realize).

![devpics.webp](https://cdn.hashnode.com/res/hashnode/image/upload/v1664793410463/nmJZMUmSj.webp align="left")



## The Eight Phases of Contribution

>Before moving forward note that I am using Gitbash for demonstration in the below section. You can download the GitBash from [here]( https://git-scm.com/downloads )

In summary, if you want to contribute to a project, the simplest way is to:

### Step 1. Find a project you want to contribute to
Find a project you want to contribute to below is an example of my repo

%[https://github.com/Younus-Saberi/GetStartedwithOS]

you can try it to get hands-on experience on GitHub

### Step 2.Fork it

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664789111339/lcA7vrAT9.png align="left")

The repo will be forked to your GitHub repo and you can start to add the project to your local system


### Step 3.
Clone it to your local system

Open git bash and type these command

```git clone https://github.com/<Username>/<RepoName>/```

In my case it is 

```git clone https://github.com/Younus-Saberi/GetStartedwithOS```

Later open the project via any code editor , I am using the VScode Editor


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664790429156/3tTUcaE0G.png align="left")


### Step 4.  Make a new branch
 
Branch help to keep your code separate from the main branch and Later help the maintainer to easily merge your pull request(pr) into their main branch

Below is the command to make a branch and switch on it directly

```git checkout -b <branch_name>```

in my case, I am creating a branch with the name new_branch

```git checkout -b new_branch```

Create a new remote for the upstream repo with the command:

```git remote add upstream https://github.com/Younus-Saberi/GetStartedwithOS```
In this case, "upstream repo" refers to the original repo you created your fork from.



### Step 5.  Make your changes

You need to make changes as per the task assigned to you. If you're following my repo you can add your GitHub username, skills and any message you would to share. After changes have been done you need to add the file in the stagging state below is the command for it

```git add <Filename>```

In my case it is 

```git add contribute.md```


``` 
Younus@MSI MINGW64 ~/OneDrive/Desktop/GetStartedwithOS (new_branch)
$ git status
On branch new_branch
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   contribute.md

no changes added to commit (use "git add" and/or "git commit -a")

Younus@MSI MINGW64 ~/OneDrive/Desktop/GetStartedwithOS (new_branch)
$ git add contribute.md

``` 


### Step 6.  Push it back to your repo

You can need to commit the changes before pushing them to the main branch 
```git commit -m "first commit"```

Later push the code to the main branch

```git push -u origin new_branch```

It will show a corresponding output if all the things went well


```
$ git push -u origin new_branch
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 332 bytes | 332.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: 
remote: Create a pull request for 'new_branch' on GitHub by visiting:
remote:      https://github.com/Younus-Saberi/GetStartedwithOS/pull/new/new_branch
remote:
To https://github.com/Younus-Saberi/GetStartedwithOS
 * [new branch]      new_branch -> new_branch
Branch 'new_branch' set up to track remote branch 'new_branch' from 'origin'.

``` 




### Step 7.  Click the Compare & pull request button
You will see a pull request notification on your fork repository, you can click on Compare and pull request

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664792362526/ThAixMZM_.png align="left")
### Step 8.  Click Create a pull request to open a new pull request


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664792404651/lo89vGeEm.png align="left")

And That's how you have created your first Pull Request 💫🚀

If the maintainer asks for changes, repeat steps 5 and 6 to add more commits to your pull request and later he will merge your PR if all changes look alright

Happy coding!



![giphy.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1664794453052/_OhviGh1R.gif align="left")


If you find any changes or mistakes in the above blog, feel free to contact [me](https://twitter.com/younussaberi). 



