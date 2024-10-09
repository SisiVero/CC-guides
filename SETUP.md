### Search portal setup

## A step by step guide to setting up [Search portal](https://github.com/creativecommons/search) locally

- Fork the repository
- Clone the forked repo, Run this on your VsCode or preferred terminal `git clone <forked repo>`
- Add remote upstream `git remote add upstream https://github.com/creativecommons/search>`
- Create a new branch for the issue you want to work on `git checkout <branch name>`
- Open the command prompt(cmd) as an administrator.
- Install WSL (Windows Subsystem for Linux) by running: wsl --install. This also installs the virtual machine platform and Ubuntu.
- Download and install Docker Desktop from here
- After Installation, restart your PC.
- Upon restarting, the CMD will launch Ubuntu and prompt you to create a user(username and password) to complete installation.
- (Optional) Install the WSL extension for VS Code for better integration.
- Open Docker Desktop
- In Vs Code terminal, `run docker compose up`

Once everything runs successfully, go to `localhost:8080` on your browser and you'll see the search portal running locally.

You can now make changes where necessary.

I hope this helps someone and happy contributing!
