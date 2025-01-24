# Setting up a dev container for Rust 

* Primary author: [Rachit Bajpai](https://github.com/rbajpai-unc)
* Reviewer: [Rishyendra Medamanuri](https://github.com/rishyendra333)

# Prerequisites
* In order to complete this tutorial you must have the following:
    1. A Github Account
    2. Visual Studio Code installed
    3. Git installed
    4. Docker Installed

# Creating a Dev Container
* Prior to coding in Rust, we will setup our Dev container. 
    1. Open visual studio code and make sure you can see the task bar to the left. 
    2. Hit the extensions button which is the 6th button down on the task bar. It should look like one cube seperated from 3 other cubes. 
    3. After finding the extensions, seach for the Dev Containers extension and install it
    4. We will also add an another extension called rust-analyzer
    5. Create a .devcontainer folder within your project and create a file within the .devcontainer directory called devcontainer.json.
    6. This file configures your development environment and you should add 
        ``` {
	            "name": "Rust",
                "image": "mcr.microsoft.com/devcontainers/rust:1-1-bullseye",
            } ``` 
    7. Now we will reopen the project within the Dev Container. Reopen the project by pressing ``` Ctrl+Shift+P (or Cmd+Shift+P on Mac) ``` and select Dev Containers: Reopen in Container
    8. Once the setup completes, open a new terminal and try running ``` rustc --version ```
        