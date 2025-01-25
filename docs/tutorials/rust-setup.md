# Setting up a dev container for Rust 

* Primary author: [Rachit Bajpai](https://github.com/rbajpai-unc)
* Reviewer: [Rishyendra Medamanuri](https://github.com/rishyendra333)

# Prerequisites
* In order to complete this tutorial you must have the following:
    1. A Github Account
    2. Visual Studio Code installed
    3. Git installed
    4. Docker Installed

# Initiliazing Git Repository
* We will create a local directory and connect it to a remote git repo
    1. Open visual stuido code and open the terminal
    2. Now we will create a new directory(folder) for our project
        ```
        mkdir rust-tutorial
        cd rust-tutorial
        ```
    3. We can then initiliaze the new repository
        ```git init```
    4. For now we will just add a Readme.md to the directory
        ```
        echo "Readme for Rust Totorial at: https://rbajpai-unc.github.io/comp423-course-notes/tutorials/rust-setup/" > README.md
        git add README.md
        git commit -m "Initial commit with README"
        ``` 
* Now we will create a Remote Repository and Link it to our Local Repo
    1. Login to Github and head over to Create a New Repository
    2. You can Fill in the details:
        Repository Name: Basic-Rust-Tutorial
        Description: "Creating Hello World in Rust"
        Visibility: Public (Depends on your preference)
    3. Do not initialize the repeo with a readme, .gitignore, or license.
    4. Hit Create Repository
    5. Go back to the terminal within vscode and add the Github repo as a remote:
        ```
        git remote add origin https://github.com/<your-username>/Basic-Rust-Tutorial
        ```
        !!! note
            Make sure to replace <your-username> with your git username
    6. We can now push our commit we made earlier with 
    ``` git push --set-upstream origin main```
# Creating a Dev Container
* Prior to coding in Rust, we will setup our Dev container. 
    1. Open visual studio code and make sure you can see the task bar to the left. 
    2. Hit the extensions button which is the 6th button down on the task bar. It should look like one cube seperated from 3 other cubes. 
    3. After finding the extensions, seach for the Dev Containers extension and install it
    4. We will also add an another extension called rust-analyzer
    5. (A) Open the rust-tutorial folder by clicking file and then open folder
     
        (B) Create a .devcontainer folder within your project and create a file within the .devcontainer directory called devcontainer.json.
    6. This file configures your development environment and you should add 
        ``` 
        {
	            "name": "Rust",
                "image": "mcr.microsoft.com/devcontainers/rust:1-1-bullseye"
        }
        ``` 
        !!! note
            This configuration file is important since it pulls the base image which contains Rust and adds it to the Dev Container. This specific configuration file creates a dev container named Rust which contains the base image.
    7. Now we will reopen the project within the Dev Container. Reopen the project by pressing ``` Ctrl+Shift+P (or Cmd+Shift+P on Mac) ``` and select Dev Containers: Reopen in Container
    8. Once the setup completes, open a new terminal and try running ``` rustc --version ```
    9. Ensure that the terminal outputs some version of Rust
        ex: ```rustc 1.83.0 (90b35a623 2024-11-26)```
# Creating the Hello COMP423 with Rust
1.  Open the terminal and create a new project names Hello-Comp423 by running
    ```cargo new Hello-Comp423 --vcs none ```
2. This should create a new directory called Hello-Comp423. Navigate to Hello-Comp423/src/main.rs where you should see code for a basic hello world. Change this to 
    ```
    fn main() {
    println!("Hello COMP423");
    }
    ```
3. After that enter the new directory, build, and run the code:
    ```
    cd Hello-Comp423
    cargo build
    cargo run
    ```
4. We will now push the changes us to the remote repository
    ```
    git add .
    git commit -m "Finished Hello Comp423"
    git push -u origin main
    ```
        