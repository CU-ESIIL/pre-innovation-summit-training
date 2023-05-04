Github essentials
================

## I. Introduction (2 minutes)

### A. Brief overview of GitHub:

GitHub is a web-based platform that provides version control and
collaboration features using Git, a distributed version control system.
It enables developers to work together on projects, track changes to
code, and efficiently manage different versions of the project. GitHub
is widely used in the software development industry and is an essential
tool for collaborative projects and maintaining code quality.

### B. Introduce GitHub Desktop and JupyterHub GitHub widget:

GitHub Desktop is a graphical user interface (GUI) application that
simplifies working with Git and GitHub by providing a more visual and
intuitive way to manage repositories, branches, commits, and other Git
features. JupyterHub GitHub widget, on the other hand, is a built-in
widget that integrates Git and GitHub functionality directly into
Jupyter notebooks, allowing users to perform version control and
collaboration tasks within the Jupyter environment. Both tools help
streamline the process of working with GitHub and make it more
accessible to users with varying levels of experience with Git and
version control.

#### 1. Download GitHub Desktop

##### Step 1: Download GitHub Desktop

Go to the GitHub Desktop download page: https://desktop.github.com/

Click on the “Download for Windows” or “Download for macOS” button,
depending on your operating system. The download should start
automatically.

##### Step 2: Install GitHub Desktop

For Windows:

Locate the downloaded installer file (usually in the Downloads folder)
and double-click on it to run the installer.

Follow the installation instructions that appear on the screen,
accepting the default settings or customizing them as desired.

Once the installation is complete, GitHub Desktop will launch
automatically. For macOS:

Locate the downloaded .zip file (usually in the Downloads folder) and
double-click on it to extract the GitHub Desktop application.

Drag the extracted “GitHub Desktop” application into the “Applications”
folder.

Open the “Applications” folder and double-click on “GitHub Desktop” to
launch the application.

##### Step 3: Set up GitHub Desktop

When GitHub Desktop launches for the first time, you will be prompted to
sign in with your GitHub account. If you don’t have one, you can create
one at https://github.com/join.

Enter your GitHub username (or email) and password, and click on “Sign
in.”

You will then be prompted to configure Git. Enter your name and email
address, which will be used for your commit messages. Click “Continue”
when you’re done. Choose whether you want to submit usage data to help
improve GitHub Desktop. Click “Finish” to complete the setup.

Now, you have successfully installed and set up GitHub Desktop. You can
start using it to clone repositories, make changes, commit, and sync
with the remote repositories on GitHub.

#### 1. Download GitHub for JupyterHub cloud service

### Step 1: Accessing JupyterHub on the cloud

Visit the JupyterHub cloud service you want to use (e.g., Binder, Google
Colab, or a custom JupyterHub deployment provided by your organization).

Sign in with your credentials or authenticate using a third-party
service if required.

### Step 2: Launch a new Jupyter Notebook or open an existing one

Click on the “New” button (usually located in the top right corner) and
select “Python” to create a new Jupyter Notebook or open an existing one
from the file browser.

Once the notebook is open, you will see the Jupyter Notebook interface
with the familiar cells for writing and executing code.

### Step 3: Install and enable the JupyterLab Git extension

In your Jupyter Notebook, create a new code cell and run the following
command to install the JupyterLab Git extension:

!pip install jupyterlab-git

Restart the Jupyter Notebook server for the changes to take effect.

### Step 4: Using the JupyterHub GitHub widget

In the Jupyter Notebook interface, you should now see a Git icon on the
left sidebar. Click on it to open the GitHub widget.

To clone a repository, click on the “+” icon in the GitHub widget and
enter the repository URL. This will clone the repository into your
JupyterHub workspace. You can now navigate through the cloned
repository, make changes, and use the GitHub widget to stage, commit,
and push your changes back to the remote repository.

To create and manage branches, use the branch icon in the GitHub widget.
You can create new branches, switch between branches, and merge branches
using this interface.

To sync your local repository with the remote repository, use the “Pull”
and “Push” buttons in the GitHub widget.

Now, you know how to access and use the JupyterHub GitHub widget running
on the cloud. This allows you to work with Git and GitHub directly from
your Jupyter Notebook interface, streamlining your workflow and making
collaboration easier.

### C. GitHub in Rstudio:

Integrating GitHub with RStudio allows users to manage their Git
repositories and collaborate on projects directly within the RStudio
environment. It offers similar functionality to GitHub Desktop but
caters specifically to R users working within RStudio. By configuring
RStudio to work with Git, creating or opening RStudio projects, and
linking projects to GitHub repositories, users can enjoy a seamless
workflow for version control and collaboration. RStudio’s Git pane
enables users to stage, commit, and push changes to remote repositories,
as well as manage branches and sync local repositories with remote ones,
providing a comprehensive solution for R developers working with GitHub.

#### Step 1: Install Git

Before integrating GitHub with RStudio, you need to have Git installed
on your computer. Visit the official Git website (https://git-scm.com/)
to download and install the latest version of Git for your operating
system.

#### Step 2: Configure RStudio to work with Git

Open RStudio.

Go to “Tools” \> “Global Options” in the top menu. In the “Global
Options” window, click on the “Git/SVN” tab.

Check that the “Git executable” field is pointing to the correct
location of the installed Git. If not, click “Browse” and navigate to
the location of the Git executable file (usually found in the “bin”
folder of the Git installation directory).

Click “OK” to save the changes.

#### Step 3: Create or open an RStudio project

To create a new RStudio project, go to “File” \> “New Project” in the
top menu. You can either create a new directory or choose an existing
one for your project.

To open an existing RStudio project, go to “File” \> “Open Project” and
navigate to the project’s “.Rproj” file.

#### Step 4: Link your RStudio project to a GitHub repository

In the RStudio project, go to the “Tools” menu and select “Version
Control” \> “Project Setup.”

In the “Project Setup” window, select “Git” as the version control
system and click “OK.”

A new “.git” folder will be created in your project directory,
initializing it as a Git repository. Commit any changes you have made so
far by clicking on the “Commit” button in the “Git” pane in RStudio.

To link your local repository to a remote GitHub repository, go to your
GitHub account and create a new repository.

Copy the remote repository’s URL (e.g.,
“https://github.com/username/repository.git”).

In RStudio, open the “Shell” by going to “Tools” \> “Shell.”

In the shell, run the following command to add the remote repository:

git remote add origin https://github.com/username/repository.git

Replace the URL with the one you copied from your GitHub repository.

Push your changes to the remote repository by running the following
command in the shell:

git push -u origin master

Now, your RStudio project is linked to a GitHub repository. You can use
the “Git” pane in RStudio to stage, commit, and push changes to the
remote repository, as well as manage branches and sync your local
repository with the remote one.

By integrating GitHub with RStudio, you can streamline your workflow,
collaborate more effectively with your team, and manage your Git
repositories directly from the RStudio interface.

## II. GitHub Basics (4 minutes)

### A. Repository:

A repository, often abbreviated as “repo,” is the fundamental building
block of GitHub. It is a storage space for your project files, including
the code, documentation, and other related resources. Each repository
also contains the complete history of all changes made to the project
files, which is crucial for effective version control. Repositories can
be public, allowing anyone to access and contribute, or private,
restricting access to specific collaborators.

### B. Fork and Clone:

Forking and cloning are two essential operations for working with
repositories on GitHub. Forking creates a personal copy of someone
else’s repository under your GitHub account, enabling you to make
changes to the project without affecting the original repo. Cloning, on
the other hand, is the process of downloading a remote repository to
your local machine for offline development. In GitHub Desktop, you can
clone a repository by selecting “Clone a repository from the Internet”
and entering the repository URL. In JupyterHub GitHub widget, you can
clone a repository by entering the repo URL in the “Clone Repository”
section of the widget.

### C. Branches:

Branches are a critical aspect of Git version control, as they allow you
to create multiple parallel versions of your project within a single
repository. This is particularly useful when working on new features or
bug fixes, as it prevents changes from interfering with the main (or
“master”) branch until they are ready to be merged. Creating a new
branch in GitHub Desktop can be done by clicking the “Current Branch”
dropdown and selecting “New Branch.” In JupyterHub GitHub widget, you
can create a new branch by clicking the “New Branch” button in the
“Branches” section of the widget.

### D. Replace ‘master’ with ‘main’:

In recent years, there has been a growing awareness of the importance of
inclusive language in technology. One such example is the use of the
term “master” in the context of the default branch in a GitHub
repository. The term “master” has historical connections to the
“master/slave” file structure, which evokes an unsavory colonial past
associated with slavery. In light of this, many developers and
organizations have begun to replace the term “master” with more neutral
terms, such as “main.” We encourage you to follow this practice and
change the default branch name in your repositories from “master” to
“main” or another suitable alternative. This small change can help
promote a more inclusive and welcoming environment within the technology
community.

## III. Collaboration and Version Control (5 minutes)

### A. Commits:

Commits are snapshots of your project’s changes at a specific point in
time, serving as the fundamental building blocks of Git’s version
control system. Commits make it possible to track changes, revert to
previous versions, and collaborate with others. In GitHub Desktop, you
can make a commit by staging the changes you want to include, adding a
descriptive commit message, and clicking “Commit to \[branch_name\].” In
JupyterHub GitHub widget, you can create a commit by selecting the files
with changes, entering a commit message, and clicking the “Commit”
button.

### B. Push:

In GitHub, “push” is a fundamental operation in the version control
process that transfers commits from your local repository to a remote
repository, such as the one hosted on GitHub. When you push changes, you
synchronize the remote repository with the latest updates made to your
local repository, making those changes accessible to other collaborators
working on the same project. This operation ensures that the remote
repository reflects the most recent state of your work and allows your
team members to stay up to date with your changes. Pushing is an
essential step in distributed version control systems like Git, as it
promotes efficient collaboration among multiple contributors and
provides a centralized location for tracking the project’s history and
progress.

In GitHub, the concepts of “commit” and “push” represent two distinct
steps in the version control process. A “commit” is the action of saving
changes to your local repository. When you commit changes, you create a
snapshot of your work, accompanied by a unique identifier and an
optional descriptive message. Commits allow you to track the progress of
your work over time and make it easy to revert to a previous state if
necessary. On the other hand, “push” is the action of transferring your
local commits to a remote repository, such as the one hosted on GitHub.
Pushing makes your changes accessible to others collaborating on the
same project and ensures that the remote repository stays up to date
with your local repository. In summary, committing saves changes
locally, while pushing synchronizes those changes with a remote
repository, allowing for seamless collaboration among multiple
contributors.

### C. Pull Requests:

Pull requests are a collaboration feature on GitHub that enables
developers to propose changes to a repository, discuss those changes,
and ultimately merge them into the main branch. To create a pull
request, you must first push your changes to a branch on your fork of
the repository. Then, using either GitHub Desktop or JupyterHub GitHub
widget, you can navigate to the original repository, click the “Pull
Request” tab, and create a new pull request. After the pull request is
reviewed and approved, it can be merged into the main branch.

### D. Merging and Resolving Conflicts:

Merging is the process of combining changes from one branch into
another. This is typically done when a feature or bugfix has been
completed and is ready to be integrated into the main branch. Conflicts
can arise during the merging process if the same lines of code have been
modified in both branches. To resolve conflicts, you must manually
review the changes and decide which version to keep. In GitHub Desktop,
you can merge branches by selecting the target branch and choosing
“Merge into Current Branch.” Conflicts will be highlighted, and you can
edit the files to resolve them before committing the changes. In
JupyterHub GitHub widget, you can merge branches by selecting the target
branch in the “Branches” section and clicking the “Merge” button. If
conflicts occur, the widget will prompt you to resolve them before
completing the merge.

## IV. Additional Features (2 minutes)

### A. Issues and Project Management:

Issues are a powerful feature in GitHub that allows developers to track
and manage bugs, enhancements, and other tasks within a project. Issues
can be assigned to collaborators, labeled for easy organization, and
linked to specific commits or pull requests. They provide a centralized
location for discussing and addressing project-related concerns,
fostering collaboration and transparent communication among team
members. Using issues effectively can significantly improve the overall
management and organization of your projects.

### B. GitHub Pages:

GitHub Pages is a service offered by GitHub that allows you to host
static websites directly from a repository. By creating a new branch
named “gh-pages” in your repository and adding the necessary files
(HTML, CSS, JavaScript, etc.), GitHub will automatically build and
deploy your website to a publicly accessible URL. This is particularly
useful for showcasing project documentation, creating personal
portfolios, or hosting project demos. With GitHub Pages, you can take
advantage of the version control and collaboration features of GitHub
while easily sharing your work with others.

## V. Conclusion (2 minutes)

### A. Recap of the essentials of GitHub:

In this brief introduction, we have covered the essentials of GitHub,
including the basics of repositories, forking, cloning, branching,
commits, pull requests, merging, and resolving conflicts. We have also
discussed additional features like issues for project management and
GitHub Pages for hosting websites directly from a repository.

### B. Encourage further exploration and learning:

While this introduction provides a solid foundation for understanding
and using GitHub, there is still much more to learn and explore. As you
continue to use GitHub in your projects, you will discover new features
and workflows that can enhance your productivity and collaboration. We
encourage you to dive deeper into the platform and experiment with
different tools and techniques.

### C. Share resources for learning more about GitHub:

There are many resources available for learning more about GitHub and
expanding your skills. Some popular resources include GitHub Guides
(https://guides.github.com/), which offers a collection of tutorials and
best practices, the official GitHub documentation
(https://docs.github.com/), and various online tutorials and courses. By
engaging with these resources and participating in the GitHub community,
you can further develop your understanding of the platform and become a
more proficient user.

## V. Conclusion (2 minutes)

### A. Recap of the essentials of GitHub:

In this brief introduction, we have covered the essentials of GitHub,
including the basics of repositories, forking, cloning, branching,
commits, pull requests, merging, and resolving conflicts. We have also
discussed additional features like issues for project management and
GitHub Pages for hosting websites directly from a repository.

### B. Encourage further exploration and learning:

While this introduction provides a solid foundation for understanding
and using GitHub, there is still much more to learn and explore. As you
continue to use GitHub in your projects, you will discover new features
and workflows that can enhance your productivity and collaboration. We
encourage you to dive deeper into the platform and experiment with
different tools and techniques.

### C. Share resources for learning more about GitHub:

There are many resources available for learning more about GitHub and
expanding your skills. Some popular resources include GitHub Guides
(https://guides.github.com/), which offers a collection of tutorials and
best practices, the official GitHub documentation
(https://docs.github.com/), and various online tutorials and courses. By
engaging with these resources and participating in the GitHub community,
you can further develop your understanding of the platform and become a
more proficient user.
