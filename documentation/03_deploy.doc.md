# Project Deployment
Either of these deployment actions can be triggered manually through GitHub actions on the repository. (`Build/Deploy` actions.)

## Staging
#### Instructions
Any merge to `develop` will trigger a deploy to staging.
#### URLs
[PROJECT Staging] (removed)
#### Credentials
Credentials can be found in 1Pass under "Staging CMS Superuser"

## Production
#### Instructions
Any merge to `production` will trigger a deploy to staging.

1. Create a release branch off of `develop`
1. Naming convention: `release/project-v1.0.0`
1. Create pull request from release branch pointed at `production`
1. Once checks pass on release pull request, merge into `production`

**NOTE:** There are currently no naming conventions established in the codebase prior to these guidelines. (As of 2023-07-20) Recommendations made here would be establishing patterns after that point.
#### URLs
[PROJECT Production] (removed)
#### Credentials
Credentials can be found in 1Pass under "PROJECT-superuser"