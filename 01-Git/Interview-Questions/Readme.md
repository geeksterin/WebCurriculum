# Important Interview Questions of Git and Github

<hr>

- [GIT MCQ's](#git-mcq)

- [What is the command to write a commit message in Git?](#what-is-the-command-to-write-a-commit-message-in-git)

- [What is difference between Git vs SVN?](#what-is-difference-between-git-vs-svn)

- [What do you understand by the term ‘Version Control System’?](#what-do-you-understand-by-the-term-version-control-system)

- [What is Git?](#what-is-git)

- [What is the difference between Git and GitHub?](#what-is-th-difference-between-git-and-github)

- [What is the function of ‘git config’?](#what-is-the-function-of-git-config)

- [What is Git fork? What is difference between fork, branch and clone?](#what-is-git-fork-what-is-difference-between-fork-branch-and-clone)

- [What does git clone do?](#what-does-git-clone-do)

- [What is the difference between "git pull" and "git fetch"?](#what-is-the-difference-between-git-pull-and-git-fetch)

- [What's the difference between a "pull request" and a "branch"?](#whats-the-difference-between-a-pull-request-and-a-branch)

- [How does the Centralized Workflow work?](#how-does-the-centralized-workflow-work)

- [What does git add command do?](#what-does-git-add-command-do)

- [What does the git push command do?](#what-does-git-push-command-do)
 
<hr>


## Git mcq

 1. Git is a __________


- A.Distributed version control system

- B.Centralized version control system

- C.Localized version control system

- D.All of the above

<details><summary><b>Answer</b></summary>
<p>

##### Answer: A

Distributed version control system

</p>

</details>

---
 2. The main objectives of Git are -
 - A. speed
 - B. data integrity
 - C. support for distributed non-linear workflows
 - D. All of the above

<details><summary><b>Answer</b></summary>
<p>

##### Answer: D

All of the above

</p>

</details>

---
3. Git is a .................... Version Control tool.
 - A. Decentralized
 - B. Centralized
<details><summary><b>Answer</b></summary>
<p>

##### Answer: A

 Decentralized

</p>

</details>

---
 4. Which Command is used to show limited number of commits?
 
 - A. git fetch
 - B. git log -n
 - C. git config
 - D. git status

<details><summary><b>Answer</b></summary>
<p>

##### Answer: B

git log -n Command is used to show limited number of commits.

</p>

</details>

---
5. Which of these Git client commands creates a copy of the repository and a working directory in the client’s workspace.

 - A. checkout
 - B. clone
 - C. import
 - D. update

<details><summary><b>Answer</b></summary>
<p>

##### Answer: B

clone

</p>

</details>

---
06. In Git, if you want to make your local repository reflect changes that have been made in a remote (tracked) repository, you should run the pull command
- A. True
- B. False

<details><summary><b>Answer</b></summary>
<p>

##### Answer: A

True

</p>

</details>

---

07. Which of the following command line environment is used for interacting with Git ?
- A. Git Bash
- B. GitHub
- C. Git Boot
- D.  Git Lab

<details><summary><b>Answer</b></summary>
<p>

##### Answer: A

Git Bash command line environment is used for interacting with Git .

</p>

</details>

---

8. _____________ command renames the current branch to <branch>

- A. git remote rm
- B. git branch -m
- C. git branch -D (CAPS)
- D. git rebase

<details><summary><b>Answer</b></summary>
<p>

##### Answer: B

git branch -m command renames the current branch to

</p>

</details>

---



### What is the command to write a commit message in Git?

Use:
```sh
git commit -a
```

 -a on the command line instructs git to commit the new content of all tracked files that have been modified. You can use 
```sh
git add <file>
```
or 
```sh
git add -A
```

before git commit -a if new files need to be committed for the first time.

<hr>

### What is difference between Git vs SVN?

Git is a distributed version control system (DVCS), whereas SVN is a centralised version control system. This is the fundamental difference between Git and SVN.

<hr>

### What do you understand by the term Version Control System?

Software technologies called version control systems assist software development teams in tracking changes to source code over time. Version control systems enable software teams to operate more swiftly and intelligently as development environments have increased.

<hr>

### What is Git?

Git is a Distributed Version Control system (DVCS). It can track changes to a file and allows you to revert back to any particular change.
It is a version control system that can efficiently manage small to very large projects and is free and open-source. Git is a tool used to log source code changes, allowing several engineers to collaborate on non-linear development.

The fact that it does not rely on a single server to store all the versions of a project's files is one of its distributed architecture's numerous advantages over other Version Control Systems (VCS) like SVN.

<hr>

### what is th difference between git and github?

Git is a version control tool that enables you to manage and monitor the history of your source code. Manage Git repositories using GitHub, a cloud-based hosting service. Git-based open-source projects can be managed more effectively using GitHub if you have any.

<hr>

### what-is-the-function-of-git-config
Git configuration values can be set at the global or project level with the git config command, which is a handy function. These settings are represented by text files with the extension. git-config. A configuration text file will be modified when git config is run.

<hr>

### What is Git fork? What is difference between fork, branch and clone?

* A **fork** is a remote, server-side copy of a repository, distinct from the original. A fork isn't a Git concept really, it's more a political/social idea. 
* A **clone** is not a fork; a clone is a local copy of some remote repository.  When you clone, you are actually copying the entire source repository, including all the history and branches.
* A **branch** is a mechanism to handle the changes within a single repository in order to eventually merge them with the rest of code. A branch is something that is within a repository. Conceptually, it represents a thread of development.

<hr>

### what-does-git-clone-do
A branch within a repository or a single repository can be copied using the git clone command. A distributed version control system is called Git. By cloning, you can take full advantage of a repository's benefits on your personal computer.

<hr> 

### What is the difference between "git pull" and "git fetch"?

In the simplest terms, `git pull` does a `git fetch` followed by a `git merge`.

* When you use `pull`, Git tries to automatically do your work for you. **It is context sensitive**, so Git will merge any pulled commits into the branch you are currently working in.  `pull` **automatically merges the commits without letting you review them first**. If you don’t closely manage your branches, you may run into frequent conflicts.

* When you `fetch`, Git gathers any commits from the target branch that do not exist in your current branch and **stores them in your local repository**. However, **it does not merge them with your current branch**. This is particularly useful if you need to keep your repository up to date, but are working on something that might break if you update your files. To integrate the commits into your master branch, you use `merge`.

<hr>

### What's the difference between a "pull request" and a "branch"?

* A **branch** is just a separate version of the code.

* A **pull request** is when someone take the repository, makes their own branch, does some changes, then tries to merge that branch in (put their changes in the other person's code repository).

<hr>

### How does the Centralized Workflow work?

The **Centralized Workflow** uses a central repository to serve as the single point-of for all changes to the project. The default development branch is called master and all changes are committed into this branch.

Developers start by cloning the central repository. In their own local copies of the project, they edit files and commit changes. These new commits are stored locally.

To publish changes to the official project, developers *push* their local master branch to the central repository. Before the developer can publish their feature, they need to *fetch* the updated central commits and rebase their changes on top of them. 

Compared to other workflows, the Centralized Workflow has no defined pull request or forking patterns. 

<hr>

### what-does-git-add-command-do
The git add command adds a change in the working directory to the staging area. It tells Git that you want to include updates to a particular file in the next commit. However, git add doesn't really affect the repository in any significant way—changes are not actually recorded until you run git commit .

<hr>

### what-does-git-push-command-do?

The git push command is used to upload local repository content to a remote repository. Pushing is how you transfer commits from your local repository to a remote repo.

<hr>

<p align="center" text="bold">
 We wish you success in all of your upcoming interviews👍😊.
</p>
