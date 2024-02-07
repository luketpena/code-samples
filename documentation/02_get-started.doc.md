# Get Started

## Backend

- **Local database**
  - Instructions for setting up can be found in [setup.doc.md](./01_setup.doc.md)
  - After this is done, the docker container should be running & the database setup + seeded
  - If you haven't already, open Docker then run `docker compose up` in a terminal within the project
- **API v1**
  - Run `nvm use`
  - Run `npm run sqlproxy` or `npm run sqlproxy:staging`
  - In a new terminal, run `npm run start`
  - There are scripts to run the proxy and api concurrently (`npm run start develop`). The choice to run them independently or concurrently is up to personal preference.
  - Can be run via debugger (`APIv1: static`)
  - **IMPORTANT:** Confirm that you are running the correct version of node with `nvm use` before starting the api. If the wrong version of node is used, it will start of but fail silently. (Requests will not resolve.)
- **API v2**
  - Run `npm run start:dev`
  - **NOTE:** If the sql proxy has not been run from v1 yet, it can be started from v2 as well (`npm run sqlproxy` or `npm run setup`)
- **API v3**
  - Run `npm run start:dev`

## Frontend

- **web**
  - Run `npm run start:cms` to start the admin dashboard
- **ionic**
  - Run `npm run start` to start the mobile app
- **tv-app**
  - Run `npm run dev` to start the tv app
