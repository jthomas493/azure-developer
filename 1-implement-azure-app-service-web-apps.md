# AZ-204 Implement Azure App Service web apps

### Explore Azure App Service

**Azure App Service** an http based service for hosting web applications, Rest apis, and mobile back ends can develop in favorite programming language or framework.

**built-in auto scale support** - abilit to scale up/down in/out - can scale the resources of the underlying machine hosting the web app.

**container support** - can deploy and run containerized web apps on windows and linux. can pull images from a private azure container registry or docker hub. can also support multi-container apps, windows containers, and docker compose for orchestration container instances

**continuous integration/ deployment support** provides out the box continuous integration and deployment with azure devops services, github, bitbucket, ftp, or local git repositories on dev machine

**deployment slots** when you deploy your webapp you can use a seperate deployment slot instead of the default production slot when running the standard app service plan tier or better. deployment slots are live apps with their own host names. app content and configurations elements can be swapped between two deployment slots.

**app service on linux** can also host web apps natively on Linux for supported application stack. custom linux containers.

**limitations** app service on linux has the following limitations

- app service on linux isn't supported on shared pricing tier
- the protal shows only features that currently work for linux app
- when deployed to built-in images, your code and content are allocated a storage volume for web content, backed by azure storage. may have disk latency

Each app service plan defines:

- operating system
- region
- number of vm instances
- size of vm instances
- pricing tier

in the free and shared tiers an app recieves CPU minutes on a shared vm instance and can't scale out. in other tiers an app runs and scales

isolate your app into a new app service plan when:

- the app is resource-intensive
- you want to scale the app independently from the other apps in the existing plan
- the app needs resource in a different geographical region

**Automated deployment** - or continuous deployment is a process used to push out new features and bug fixes in a fast and repetitive pattern with minimal effect on end users

- azure devops
- github
- bitbucket

**manual deployment** - manually push code to azure

- git
- CLI
- Zip deploy
- FTP/S

**continuously deploy containers** - deploy the image into a staging slot and swap into production to prevent downtime. the automation is more complex than code deployment because you must push the image to a container registry and update the image tag on the webapp

- build and tag the image
- push the tagged image
- update the deployment slot with the new image tag
