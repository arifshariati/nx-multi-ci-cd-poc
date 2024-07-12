# Nx multi CI/CD POC

This repo presents the basic configuration of Nx monorepo containing several apps. In production, we need a mechanism of deploying various applications to various cloud providers.
In this repo we shall deploy NestJS backend application to `Heroku` where as the NextJS frontend application to `Vercel`.

> ## How it should work?
>
> We start working on a feature in Nx workspaces containing several apps and libraries. Let's present two use cases in production.
>
> ### 1. Only frontend `NextJs` app has new changes
>
> Either we have minor fix on frontend or introducing fully fledge feature on frontend. When our CI/CD pipeline runs, only frontend app deployment shall happen.
>
> ### 2. Both or several apps has new chanegs
>
> The introduction of our new changes are present in both or almost all the apps inside our Nx workspaces. The CI/CD pipeline should run on all the apps and libraries.

> ## But Why?
>
> This is part of CI/CD optimization, including Nx workspace caching where we want to avoid running heavy runners behind the scene. Rather we run CI/CD runners for only affected codebase and perform deployment.

## Tech Stack

    1. Nx worksapces
    2. NextJS
    3. NestJS

## Useful commands

```Bash
# Add NextJS plugin
npx nx add @nx/next

# Add NextJS application 
npx nx generate @nx/next:application --name=frontend --directory=apps/frontend --projectNameAndRootFormat=as-provided --no-interactive

# Run NextJs application 
npx nx run frontend:dev

# Add NestJS plugin
npx nx add @nx/nest
```
