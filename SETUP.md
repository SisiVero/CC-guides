# Setting up CreativeCommons/SearchPortal

 A step by step guide to setting up [Search portal](https://github.com/creativecommons/search) locally

 ## Installation Guides

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



# Setting Up CreativeCommons/LegalDB

A comprehensive guide for setting up the [creativecommons/Legaldb](https://github.com/creativecommons/legaldb) project on your local machine.

## Prerequisites

- [Git](https://git-scm.com/downloads)
- [Docker](https://www.docker.com/)
- Terminal access (see specific requirements for different operating systems below)
- Text editor (e.g., VS Code)

## Installation Steps

### 1. Fork the Repository

Visit the [creativecommons/Legaldb](https://github.com/creativecommons/legaldb) GitHub page and click the "Fork" button to create your own copy of the repository.

### 2. Configure git properly on your local machine

#### Important Note for Windows Users
This is step is very important because it ensures that the LF line endings of the files in the repo and maintained and not converted to the windows CRLF line endings

#### For Unix-based Systems (Mac/Linux)
This step is not as important, but you can still run this command

Use any terminal of your choice to run this command

```bash
git config --global core.autocrlf input
```

### 2. Clone the Repository

Use any terminal of your choice to run this command

```bash
git clone https://github.com/[your-github-username]/legaldb.git
```

### 3. Set Up Development Environment

#### Prerequisites Check
Ensure you have reviewed the foundational tech requirements and have Docker installed on your system. Visit the [Docker website](https://www.docker.com/) for installation instructions if needed.

#### Environment Configuration

1. Create a `.env` file:
   - Locate the `.env.template` file in the cloned repository
   - Create a new file named `.env`
   - Copy the contents from `.env.template` to `.env`
   - Configure the following variables:

```env
DJANGO_SECRET_KEY="your_random_string"
DJANGO_DEBUG_ENABLED=True
DJANGO_DATABASE_PASSWORD=postgres  # or your chosen password
DJANGO_SUPERUSER_PASSWORD="your_chosen_password"
DJANGO_TIME_ZONE="UTC"
DJANGO_SECURE_SSL_REDIRECT=false
DJANGO_COMPRESS_ENABLED=true
DJANGO_COMPRESS_OFFLINE=false
LIBSASS_OUTPUT_STYLE=
```

#### Start the Development Environment

1. Navigate to the project directory containing the `docker-compose.yml` file
2. Run the Docker Compose command:
```bash
docker compose up
```

> **Note**: Initial setup will take some time as it downloads required containers (~2.6GB for app and ~350MB for db containers)

3. Apply database migrations (in a new terminal):
```bash
docker compose exec app ./manage.py migrate
```

### 4. Accessing the Application

Once everything is set up, access the application at:
```
http://127.0.0.1:8000
```

> **Note**: While the terminal may display `http://0.0.0.0:8000`, use `127.0.0.1:8000` in your browser.

## Troubleshooting

### CRLF Line Ending Issues
If you encounter the following error:
```
/usr/bin/env: 'python3\r': No such file or directory
/usr/bin/env: use -[v]S to pass options in shebang lines
```
This indicates CRLF line ending issues. Solution:
1. Go to the manage.py file in the repo
2. Check the line ending sequence at the bottom left of your code editor (this is the location in vs code) and ensure its LF and not CRLF
3. Do the same thing in step 2 for your `Dockerfile` and your `docker-compose.yml` file
4. Go back to your terminal and run `docker compose build`
5. Finally, run `docker compose up`
6. And your're all set, the application should be running fine now!

## Acknowledgments

Original documentation by Victor Egbadon. I would also love to acknowlege Fatuma Abdulahi for insight on the setting up of the env variables.
