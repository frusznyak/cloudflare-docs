---
updated: 2020-09-22
difficulty: Beginner
pcx-content-type: tutorial
---

# Migrating from Netlify to Pages

In this tutorial, you'll learn how to deploy your Netlify application to Cloudflare Pages.

<Aside>
You should already have an existing project deployed on Netlify that you'd like to host on Cloudflare Pages. Features such as Netlify's Forms and Serverless Functions are currently not supported in Cloudflare Pages.
</Aside>

## Finding your build command and build directory

To move your application to Cloudflare Pages, you'll need to find your build command and build directory. Cloudflare Pages will use this information to build your application and deploy it.

In your Netlify Dashboard, find the project that you want to deploy. It should be configured to deploy from a GitHub Repo.

![Selecting a site in the Netlify Dashboard](./netlify-deploy-1.png)

Inside of your site dashboard, select "Site Settings", and then "Build & Deploy".

![Selecting Site Settings in site dashboard](./netlify-deploy-2.png)

![Selecting Build and Deploy in sidebar](./netlify-deploy-3.png)

In the "Build & deploy" tab, find the "Build settings" panel, which will have the **Build command** and **Publish directory** fields. Save these for deploying to Cloudflare Pages! In the below image, my **Build command** is `yarn build`, and my **Publish directory** is `build/`.

![Finding the "Build command" and "Publish directory" fields](./netlify-deploy-4.png)

## Creating a new Pages project

Once you've found your build directory and build command, you can move your project to Cloudflare Pages.

The [Getting started guide](/getting-started) will show you how to add your GitHub project to Cloudflare Pages.

If you choose to use a custom domain for your Pages, you can set it to the same custom domain as your currently deployed Netlify application. When Pages finishes the initial deploy of your site, you will need to delete the Workers application to start sending requests to Cloudflare Pages.

## Cleaning up your old application and assigning the domain

In your DNS settings for your domain, make sure that you've updated the CNAME record for your domain from Netlify to Cloudflare Pages. With your DNS record updated, requests will go to your Pages application.

Congrats! You've migrated your Netlify project to Cloudflare Pages.
