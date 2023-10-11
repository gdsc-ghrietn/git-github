# Hands on Learning of Git and Github
Date: 14th October 2023

Speaker: [@sahilyeole](https://github.com/sahilyeole)

Event page (register here): https://gdsc.community.dev/events/details/developer-student-clubs-g-h-raisoni-institute-of-engineering-and-technology-presents-hands-on-learning-of-git-and-github/
## Topics to be covered
- [Setting up git and github](https://github.com/gdsc-ghrietn/git-github#setting-up-git-and-github)
- [Basic terminal commands for navigation](https://github.com/gdsc-ghrietn/git-github#basic-terminal-commands-for-navigation)
- [What is version control system?](https://github.com/gdsc-ghrietn/git-github#what-is-version-control-system)
- [Creating & cloning a repository](https://github.com/gdsc-ghrietn/git-github#creating--cloning-a-repository)
- [Making changes](https://github.com/gdsc-ghrietn/git-github#making-changes)
- [Pushing changes to github ](https://github.com/gdsc-ghrietn/git-github#pushing-changes-to-github)
- [Git branches and merging](https://github.com/gdsc-ghrietn/git-github#git-branches-and-merging)
- [Creating a pull request](https://github.com/gdsc-ghrietn/git-github#creating-a-pull-request)
- [Making your first open source contribution [Activity]](https://github.com/gdsc-ghrietn/git-github#making-your-first-open-source-contribution-activity)

#### BONUS
- [Resolving merge conflicts](https://github.com/gdsc-ghrietn/git-github#resolving-merge-conflicts)
- [VS code integration with git](https://github.com/gdsc-ghrietn/git-github#vs-code-integration-with-git)

---
## Setting up git and github
- Creating github account: https://github.com/signup
- Downloading git: https://git-scm.com/downloads
- Installing git (guide): https://phoenixnap.com/kb/how-to-install-git-windows

  Note: In that guide, ignore `How to Launch Git in Windows` and later.
- Make sure `git -v` command works in your terminal. If it doesn't, there might be some problem with the installation or in setting up the path. Try reinstalling git and make sure to follow the guide properly.

---
## Basic terminal commands for navigation
**NOTE:** For Windows users, use `Git Bash` for running the commands. It comes with the git installation. For this session, we will be using `Git Bash` for running the commands.
- 
1. `pwd` (Print Working Directory): Displays the current directory path.

   Example:
   ```bash
   $ pwd
   /home/user/documents
    ```
2. `cd` (Change Directory):
    - To move forward (into a subdirectory):
      ```bash
      $ cd directory_name
      ```
    - To move backward (up one directory):
      ```bash
      $ cd ..
      ```
    - To move up two directories:
      ```bash
      $ cd ../..
      ```

3. `ls` (List): Lists the files and directories in the current directory.

    Example:
    ```bash
   $ ls
    file1.txt file2.txt directory1 directory2
    ```
---
## What is version control system?
- Version control systems are software tools that help software teams manage changes to source code over time.
- Version control systems help software teams work faster and smarter.
![Alt text](<assets/Screenshot 2023-10-10 at 5.41.57 PM.png>)
- The types of VCS are:
    1. Local Version Control System
    2. Centralized Version Control System
    3. Distributed Version Control System
- Git is the most well-known example of distributed version control systems.
![Alt text](assets/image.png)
---

## Creating & cloning a repository
### Creating a repository
1. Open your github profile and go to `Repositories` tab.
2. Click on `New` button.
![Alt text](<assets/Screenshot 2023-10-10 at 5.47.21 PM.png>)
3. Give a name to your repositor.
4. Make sure to check `Add a README file` option.
5. Click on `Create repository` button.
![Alt text](<assets/Screenshot 2023-10-10 at 5.51.09 PM.png>)

### Cloning a repository
1. After creating a repository you will be redirected to the repository page. Or else you can access it from Repositories tab in your profile.
2. Click on `Code` button.
3. Copy the https link of your repository.
![Alt text](<assets/Screenshot 2023-10-10 at 5.56.09 PM.png>)
4. Open your bash terminal and `cd` into your desired location (for me Developer folder).
```bash
$ cd Developer
```
5. Open your bash terminal and enter `git clone [your repo link]`
```bash
git clone https://github.com/sahilyeole/Test.git  
```
6. Now in your file manager you can see a new folder created with the name of your repository. You can also see this using `ls` command.

![Alt text](<assets/Screenshot 2023-10-11 at 2.09.24 PM.png>)

7. `cd` into that folder in terminal.
```bash
$ cd Test
```
8. `ls` to see the files in that folder.
```bash
$ ls
README.md
```
It will show only README.md file as we have not added any other file yet.

Congrats you have successfully cloned your first repository.

---

## Making changes
1. Open the README.md file in your favorite text editor. (Ex: VS code or notepad)
I'm vim user so I will use vim to open the file.

```bash
nvim README.md
```
2. Add some text to the file and save it.
```
Hello world
```
![Alt text](<assets/Screenshot 2023-10-11 at 2.55.45 PM.png>)

3. Now go to your terminal and type `git status` command.
```bash
$ git status
```
![Alt text](<assets/Screenshot 2023-10-11 at 2.59.31 PM.png>)
`git status` gives the current status of the repository. It shows that README.md file is modified. And it says changes not staged for commit. It means that the changes are not yet added to the staging area.

---
## Pushing changes to github
1. Now we will add our modified file to the staging area using `git add` command.
```bash
$ git add README.md
```
Staging area is a place where we add the files which are ready to be committed. We can add multiple files to the staging area and commit them all at once.

Or if you want to stage all the files in the current directory of the repository then you can use `git add .` command.
```bash
$ git add .
```
**Note:**

  `.` represents the current directory.

  You can also restore the changes you have made to the file using `git restore` command.
  (You can ignore this command for now if you dont want to restore the changes.)
  ```bash
  $ git restore README.md
  ```
2. Enter `git status` command again to see the status of the repository.
```bash
$ git status
```
![Alt text](<assets/Screenshot 2023-10-11 at 3.16.57 PM.png>)
 Now it says "Changes to be committed". It means that the changes are added to the staging area and are ready to be committed.

 At this point you can verify your changes by using `git diff` command.
 ```bash
  $ git diff
  ```

3. Now we will commit the changes using `git commit` command.

Commit is like a snapshot of the changes you have made. If we want to push the changes to github then we have to commit them first.

```bash
$ git commit -m "Added hello world"
```
`-m` flag is used to add a commit message. It is a good practice to add a meaningful commit message to every commit you make. It helps you to keep track of the changes you have made.

4. Try `git status` command again.
```bash
$ git status
```
![Alt text](<assets/Screenshot 2023-10-11 at 3.27.23 PM.png>)

Now it doesn't show any changes. It means that the changes are committed successfully.
We can verify this by using `git log` command.
```bash
$ git log
```
git log shows the history of commits made to the repository. It shows the commit hash, author, date and commit message.
![Alt text](<assets/Screenshot 2023-10-11 at 3.28.32 PM.png>)
### Note: Press `q` to exit from the log.
5. We aren't done yet because these commits are currently stored only in our local machine. We have to push these commits to github so that everyone can see them.

We will use `git push` command to push the commits to github.
```bash
$ git push origin main
```
here origin is referring to the remote repository and main is the branch name.

Or you can also use 
```bash
$ git push origin head
```
This will push to the current branch (head) you are on to the remote repository. In this case our head branch is main.

You can verify `head` branch here or even using  `git status` command.
![Alt text](<assets/Screenshot 2023-10-11 at 3.33.47 PM.png>)

6. After 5th step your commits are pushed to github. You can verify this by going to your repository page on github.
![Alt text](<assets/Screenshot 2023-10-11 at 3.36.58 PM.png>)

---

## Git branches and merging
## Creating a pull request
## Making your first open source contribution [Activity]

#### BONUS
## Resolving merge conflicts
## VS code integration with git

