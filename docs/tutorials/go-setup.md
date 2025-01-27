# Setting up a dev container for Go

* Primary author: [Riya](https://github.com/riyachawan/comp423-course-notes.git)

* Reviewer: [Shwetha](https://github.com/shwethakunjur/comp423-course-notes)


## Prerequisites

1. Have Visual Studio Code installed.
2. Install the Dev Containers extension for VS Code.
3. Have docker running. 
4. Have git installed. 

## Git initialization

1. Create a project folder
```{.yaml .copy}
mkdir HelloGo
cd HelloGo
```
2. Initialize Git
```{.yaml .copy}
git init
```


## Creating a new Dev Container Project for Go

1. Create a *.devcontainer* directory
2. Create a Dev container configuration *.devcontainer/devcontainer.json*

Here's the configuration for *devcontainer.json* file:
```{.yaml .copy}
{ 
    "name": "Go Dev Container",
    "image": "mcr.microsoft.com/devcontainers/go:0-1.19",
    "customizations": {
        "vscode": {
            "extensions": ["golang.go"]
        }
    },
    "features": {
        "ghcr.io/devcontainers/features/common-utils:2": {}
    }
}
```
This installs the official Go VSCode Plugin.

3. Open the dev container in VSCode 
4. Press **Ctrl+Shift+P** and select *Remote-Containers: Reopen in Container*


!!! Note
    Ensure Docker is running before trying to reopen

Verify the recent version of Go using:
```{.yaml .copy}
go version
```

## Basic "Hello COMP423" Program

1. Create a Go program by creating *main.go*
```{.yaml .copy}
package main
import "fmt"
func main() {
    fmt.Println("Hello COMP423")
}
```

2. Initialize the Go module system
```{.yaml .copy}
go mod init HelloGo
```

3. Run the program
```{.yaml .copy}
go run main.go
```
> This compiles and executes the main package in one step and is best used for quick testing.
It doesn't create an executable file.

4. Build a binary
```{.yaml .copy}
go build -o hello
./hello
```
> This compiles the program into a binary executable. It is similar to the gcc subcommand which creates the a.out file.
While we use the gcc subcommand for C programs, we use the build for go.




