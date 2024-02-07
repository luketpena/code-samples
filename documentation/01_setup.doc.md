# Project Setup

## Prerequisites

- Docker (Docker Desktop is preferred if you are using Mac or Windows)
- Python
- Rosetta (for m1 chips)
- Node (nvm is preferred)
- Access to PROJECT Google Cloud account

## Installing Dependencies

Run `nvm use && npm i` in each project with a package.json file.

**NOTE:** If you are using an m1 Mac, you might be unable to install versions of node prior to v15, and API v1 requires v12 and API v2 requires v14.

- Navigate to Terminal in /Applications and open info
- In info, check "Open using Rosetta"
- Restart the terminal and install the required no version

Depending on your local environment, there may be some issues with versions of node, npm, and other dependencies. As of 11/21/2022 the following versions are known to work:

- npm: 6.14.15
- node: use what's in the .nvmrc files

As always, google and your teammates are your best friend when trying to the project set up.

## Config files & .env

_All values can be found in the secret manager in the file specified per resource._

- **API v1**
  - Create an `ormconfig.json` in /api directory (`api-config-local`)
  - Create an `.env` in /api directory (`apiv1_env_local`)
  - Create `PROJECT-(removed).json` in root directory (same name in secret manager)
  - Run `npm run sqlproxy:install:mac` in /api directory (must be logged into GCP)
    - If not logged in, do so with `gcloud auth login`
    - Must have access to the project in GCP
- **API v2**
  - Create an `.env` in /apiv2 directory (`apiv2_env_local`)
  - Create `PROJECT-(removed).json` in /apiv2 directory (same name in secret manager)
- **API v3**
  - Create an `.env` in /apiv3 directory (`apiv3_env_local`)
- **TV App**
  - Create an `.env.local` in the /tv-app directory with the following values:

```
VITE_API_V3_URL=http://localhost:8082
```

## Local database and seeding

- **To set up**
  - Run `docker compose up` in the project if you haven't already
  - In /apiv3, run `npx prisma migrate dev` or `npx prisma migrate push` (generates database)
  - In /apiv3, run `npx prisma db seed` (seeds database)
- **To connect**
  - Host: `0.0.0.0`
  - Port: `5432`
  - User: `postgres`
  - Password: `postgres`
  - Database: `postgres`

_You can also view the database by running `npx prisma studio` within /apiv3_
