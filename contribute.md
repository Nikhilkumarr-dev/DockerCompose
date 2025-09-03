## Manual Installation of 
-install nodejs locally
-clone the repo
-install dependencies(npm install)
-statrt the db locally
    -docker run -e POSTGRES_PASSWORD=mysecretpassword -d -p 5432:5432 postgres
    -go to neon.tech and get ourself a new db
    -change the .env file to postgres://postgres:mysecretpassword@localhost:5432/postgres 
-Change the .env file and update your db credentials
-npx prsima migrate
-npx prisma generate
-npm run build 
-npm run start

## Docker installation
-get the docker locally to the desktop
--create a network `docker network create user_project`
-start postgres
    -run the docker image of postgres: `docker run --network user_project --name postgres -e POSTGRES_PASSWORD=mysecretpassword -d -p 5432:5432 postgres`
    -Build the image - `docker build --network=host -t user-project .`
    -start the image -`docker run -e DATABASE_URL=postgresql://postgres:mysecretpassword@postgres:5432/postgres --network user_project -p 3000:3000 user-project`

## Docker Compose installation steps
-Install docker,docker-compose
-Run `docker-compose up`