# Setting up a dev container for Rust

* Primary author: [Onyi Igwe](https://github.com/igtricia)

# Prerequisites
Before we start, make sure you have the following prequisites down:

* A GitHub account: If you don’t have one yet, sign up at [GitHub](https://github.com/).
* Git installed: [Install Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) if you don’t already have it.
* Visual Studio Code (VS Code): Download and install it from [here](https://code.visualstudio.com/).
* Docker installed: Required to run the dev container. [Get Docker here](https://www.docker.com/products/docker-desktop).

# Part 1. Project Set-Up: Creating Your Repository

(1) In your host machine's terminal, create a new directory for your project and cd into the directory. The directory is where you will directly interact with your project's files and reflects the local version of your project.
``` 
mkdir go-project
cd go-project
```
(2) Initialize a new Git repository. This git subcommand creates a new empty repository:

``` 
git init
```

(3) Create a README file
```
echo "# go-project" > README.md
git add README.md
git commit -m "Initial commit with README"
```

(3) Navigate your GitHub account to the [Create a New Repository](https://github.com/new) page and fill in the details as you wish

Link your local repository to Github using the code snippet below:
```
git remote add origin https://github.com/<your-username>/go-project
```
Note: Input your GitHub's username in the <your-username> text.

(4)Check your default branch name with the subcommand git branch. It is usually recommended to make your default branch main because later on in your project, merges and commits will be easier especially if you are collaborating with other teammates. If it's not main, rename it to main with the following command: git branch -M main

(5) Push local commits to Github repository using the code below:
```
git push --set-upstream origin main
```

# Part 2 Setting Up the Development Environment for Golang!

1. Open your go-project directory in VSCode
2. Install the Dev Containers extension for VS Code if not installed already
3. Create a .devcontainer directory in the root of your project with the following :
```
.devcontainer/devcontainer.json
```
4. Update the devcontainer.json file with the following code snippet :
