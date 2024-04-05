

## Start Development environment

1. Clone the repository
2. Create an .env file in the root directory based on the .env.template file
3. If project was cloned execute the following commands:
```bash
git submodule update --init --recursive
``` 
4. Run the following commands in the terminal:
```bash
docker compose up --build
```

### Steps to create Git Submodules

1. Create a new repository on GitHub
2. Clone the repository on your local machine
3. Add the submodule, where `repository_url` is the URL of the repository and `directory_name` is the name of the folder where you want the submodule to be saved (it should not already exist in the project)

 
```
git submodule add <repository_url> <directory_name>
```
1. Add the changes to the repository (git add, git commit, git push)
Example:
```
git add .
git commit -m "Add submodule"
git push
```

1. Initialize and update Submodules. When someone clones the repository for the first time, they should run the following command to initialize and update the submodules.
```
git submodule update --init --recursive
```
1. To update the references of the submodules
```
git submodule update --remote
```


## Important
If you are working in the repository that has the submodules, **first update and push** in the submodule and **then** in the main repository.

If done in reverse, the references to the submodules in the main repository will be lost and we will have to resolve conflicts.


## Prod build
1. Clone the repository
2. Create an .env file in the root directory based on the .env.template file
3. To run the docker container in production mode, execute the following command:

```bash
docker compose -f docker-compose.prod.yml build
```