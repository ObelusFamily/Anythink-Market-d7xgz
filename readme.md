# Welcome to the Anythink Market repo

To start the app use Docker. It will start both frontend and backend, including all the relevant dependencies, and the db.

Please find more info about each part in the relevant Readme file ([frontend](frontend/readme.md) and [backend](backend/README.md)).

## Development

When implementing a new feature or fixing a bug, please create a new pull request against `main` from a feature/bug branch and add `@vanessa-cooper` as reviewer.

## First setup

# Up and Running with WSL on Windows
Required:
- VSCode (or other editor/ide)
- Windows Terminal (or other terminal)
- WSL2
- Linux Distribution - Ubuntu is default
- Git (install both on Win and WSL Distro, use Win Credentials Manager)
- Docker Desktop
- \[Optional\] To make working with pull requests easier consider installation of GitHub CLI

As we work with Git, make sure name and email are set (on both Win and the Linux Distro):
```bash
# show configuration
git config --list

# set name & email
git config --global user.name "<your user name>"
git config --global user.email "<your email address>"
```

Because of WSL Integration we can use the Git for Windows credential helper on the distro. We do not want to enter our credentials for each git operation:
```bash
# on your linux distribution
git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/bin/git-credential-manager-core.exe"
```

Also, it is best practice to work with the files 'where they belong'. So whilst you could make the project directory live on your Windows drive it will be at a performance cost. Also some processes may not pick up changes to files. So it is best to create the project folder(s) on the Linux Distro. A typical location would be in the home directory:
```bash
$ cd ~
$ pwd
# /home/<username>

$ mkdir projects
$ cd projects
```

**Clone** the repo into the projects directory (no need to create subdir for the project itself, the cloning takes care of that. You can change the directory name as desired ):
```bash
git clone https://github.com/ObelusFamily/Anythink-Market-d7xgz.git
```

Verify that Docker is up and running
```bash
docker -v
docker-compose -v
```

From the project directory, load the project's backend and frontend:
```bash
cd Anythink-Market-d7xgz
docker-compose up
```

Test that Docker is working correctly, the backend should be running and able to connect to the local database. Point the browser to
[http://localhost:3000/api/ping](http://localhost:3000/api/ping)

**Check the frontend** and make sure it’s **connected to the backend**. If everything is working properly, you’ll be able to **create a new user** on [http://localhost:3001/register](http://localhost:3001/register)

Make sure that you **run all scripts in the next quests on one of the containers** created by `docker-compose up`. Also, **you can use `docker exec` to run commands** on a running container.

It looks like your environment is ready! 😀
