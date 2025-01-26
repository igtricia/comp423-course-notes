# Setting up a dev container for Golang!

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

(4) Navigate your GitHub account to the [Create a New Repository](https://github.com/new) page and fill in the details as you wish

Link your local repository to Github using the code snippet below:
```
git remote add origin https://github.com/<your-username>/go-project
```
Note: Input your GitHub's username in the <your-username> text.

(5)Check your default branch name with the subcommand git branch. It is usually recommended to make your default branch main because later on in your project, merges and commits will be easier especially if you are collaborating with other teammates. If it's not main, rename it to main with the following command: git branch -M main

(6) Push local commits to Github repository using the code below:
```
git push --set-upstream origin main
```
# Part 2 Setting Up the Development Environment for Golang!

(1) Open your go-project directory in VSCode

(2) Install the Dev Containers extension for VS Code if not installed already

(3) Create a .devcontainer directory in the root of your project with the following :

```
.devcontainer/devcontainer.json
```
(4) Update the devcontainer.json file with the following code snippet :
```yaml
{
  "name": "go-project",
  "image": "mcr.microsoft.com/vscode/devcontainers/go:latest",
  "customizations": {
    "vscode": {
      "settings": {},
      "extensions": [
        "golang.go"
      ]
    }
  }
}
```

<p> Name: A descriptive name for your dev container. </p>
<p> Image: The Docker image to use, in this case, the latest version of a Go environment. Microsoft maintains a collection of base images for many programming language environments, but you can also create your own! </p>
<p> Customizations: Adds useful configurations to VS Code, like installing the Go extension. When you search for VSCode extensions on the marketplace, you will find the string identifier of each extension in its sidebar. Adding extensions here ensures other developers on your project have them installed in their dev containers automatically. </p>

(5) Reopen the project in the container by pressing Ctrl+Shift+P for Windows(or Cmd+Shift+P on Mac), typing "Dev Containers: Reopen in Container," and selecting the option.

Once your dev container setup completes, close the current terminal tab (trash can), open a new terminal pane within VSCode, and try running 'go-version' to see your dev container is running a recent version of Go without much effort! (As of this writing: 1.23.5 released in January of 2025.)
