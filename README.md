# Teach-Yourself-Git
## What is Git?
Git is a popular version control system (VCS). A version control system records the changes made to code over time in a special database called repository. It helps to find who made the changes, why the changes were made, when the changes were made and what were those changes. It gives a summary of how a project evolves over time. Without a VCS, we'll have to constantly make new directories containing a full copy of the project with different names. Besides for collaboration, it will require a lot of email exchange which will be time consuming and complex.

* A version control system can be divided into two categories:
  * **Centralized:**
    In a centralized VCS, all team members remain connected to a central server. Subversion and Team Foundation Server are two examples of centralized VCS. The problem of centralized VCS is that if the server goes offline, team members are unable to collaborate and save the snapshots of their works.
  * **Distributed:**
    In distributed VCS, every team member has a copy of the project with history in their local machine. They can modify the project anytime locally and even if someone delete the project accidentally, other team members will have the copy. Two VCS of this type are - Git and Mercurial.

* **Reasons for Using Git:**
  * Free
  * Open Source
  * Super Fast
  * Scalable
  * Cheap Branching / Merging

* **Configuring Git:**
  Git needs to be configured first time we use it to specify the following settings:
  * Name
  * Email
  * Default Editor
  * Line Ending
  
  The configuration settings can be applied at three different labels:
  * **SYSTEM:** Applies to all users running the computer.
  * **GLOBAL:** Applies to all repositories of the current user.
  * **LOCAL:** Applies to the current repository only.

  #### Configuring Name:
  * If there is space in name, use " ".
  ```git
  git config --global user.name XYZ
  ```
  
  #### Configuring Email:
  ```git
  git config --global user.email xyz@gmail.com
  ```
  
  #### Configuring Editor:
  * Install an editor and add it to the path of your OS, otherwise git will use the default editor corresponding to the OS. For macOS, git uses vim editor and for linux, git uses nano.
  * In this tutorial, I'll show using VSCode. So download the VSCode editor and add it to the path so that you can open it from anywhere using terminal or command prompt.
  * Considering VSCode is installed on your machine let's configure editor.
  ```git
  git config --global core.editor "code --wait"
  ```
  * The `--wait` flag tells terminal to wait until the vscode is closed.

  #### Configuring Line Ending:
  * In windows machine, line ending can be marked by either `\r` (carriage return) or `\n` (line feed).
  * In MacOS/Linux, line ending is marked by `\n` only.
  * That means, collaborators working on different machines may end up with weird issues if line ending is not handled properly.
  * In such case, windows should configure in such a way that when code is pushed into repository, the carriage return is removed and when the code is pulled from the repository, carriage return is automatically included.
  * macOS users don't require the carriage return to be included in the code when pulled from a repository. However, if by mistake carriage is used in the code, git should remove the carriage return from it.
  * For windows users:
  ```git
  git config --global core.autocrlf true
  ```
  * For mac/linux users:
  ```
  git config --global core.autocrlf input
  ```
 * All the configurations are saved in `.gitconfig` file. It can be checked using the following command:
 ```git
 git config --global -e
 ```
 * You can always learn more about git configuration from [here](https://git-scm.com/docs/git-config).
 * Also, this page can also be explore from terminal using the command `git config --help` or `git config -h`
