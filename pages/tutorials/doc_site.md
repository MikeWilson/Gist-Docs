# Publish a doc site from Figma in about 10 minutes

As a designer, creating a design system documentation site is not something I felt I could do alone. Usually, I would partner with one or more devs to create and publish a doc site. When I added Github publishing to the[  Gist plugin](https://gist-plugin.com/), I found there was an opportunity for designers to easily create and manage their own doc site.


In this tutorial, I will show you how to create and publish your own doc site in about 10 minutes. You will:


1. Setup a[  Nextra](https://nextra.vercel.app/) repo
2. Link Figma components to Github files
3. Publish edits to those files
4. Create a new page
5. Optionally (and beyond the 10 minutes): Customize the site


FYI the methods I show in this tutorial use Gist's paid features which require a $4/month subscription.

## Setup a Nextra Repo

To start we will create a Vercel project and link it to a new Github repository that will clone a[  Nextra](https://nextra.vercel.app/) template.


1. Go to[  https://vercel.com/](https://vercel.com/mikewilson) and click '+ New Project'
2. Under 'Import Git Repository' select the link at the bottom 'Import Third-Party Git Repository'
3. Paste this URL[  https://github.com/MikeWilson/nextra-docs-empty](https://github.com/MikeWilson/nextra-docs-empty) and click 'Continue'. This is a fork of Nextra with the default content removed
4. Under 'Create Git Repository' connect your Github and give your project a name.
5. Uncheck 'Create private Git Repository' so the repo is public
6. Click 'Create' and it will deploy the blank site
7. Once deployed, click 'Go to dashboard' and then 'View Git Repository', leave this Github tab open for the next section

## Link to Github files

Now we are going to link the first page of our doc site to a frame in Figma so we can make our first edits.


1. Open[  Figma](https://www.figma.com/files/recent?fuid=919073936511062644) and select a frame you'd like to link to the index file
2. Open Gist and go to the 'Link' tab
3. Using the selector in the top right choose Github. If you are not subscribed to Gist you will be directed to Gumroad to get a license
4. Paste your repo URL in the 'URL' input
5. Type or paste pages/index.md into the 'File path' input
6. Click 'Link' and the page contents should load 🎉

## Publish Edits

Before we can publish an edit we will need to generate a Personel Access Token from Github. This token allows you to commit changes to your repository. It also allows you to control permissions on that token and revoke them at any time.


1. Go to[  https://github.com/settings/tokens](https://github.com/settings/tokens) and click 'Generate new token'
2. Name the token something like "gist plugin" so you remember where it is being used
3. Select the expiration. You will need to replace the token if it expires.
4. Give the token permission to publish by checking the 'public_repo' scope checkbox. If your repository is private it will need the full 'repo' scope. Tokens should receive the minimum scope required. Since these docs will be published to the web anyways, I recommend keeping this key to the 'public_repo' scope. Do not leave this token on components in any public Figma files.
5. Open Figma and add your newly generated key to the Gist 'Access token' input
6. Edit your introduction page
7. Click 'Publish' and it will send the doc to Github
8. Go back to your Vercel project and check for deployment, one may be building or just recently finished. Once it is finished you can click the deployment link and see your new doc live! Woo!

## Create New Page

1. Select a component in your design system
2. Fill in the Github details however this time put pages/components/component_name.md in the path and swap in your components name before the .md. Put ALL pages you'd like included in the pages/ folder. You can create folders by adding one to the path like pages/components/button.md
3. Write your component docs. The[  Gist - Getting Started file](https://www.figma.com/community/file/1123463738242107780) has a lightweight template if you're searching for a place to start
4. Publish your doc and check your Github / Vercel project to make sure the changes were picked up

Tip: Use[  Dynamic URLs](https://docs.gist-plugin.com/dynamic_URLs) and[  Templates](https://docs.gist-plugin.com/templates) to make creating new pages for components a breeze

## Customize the Site

Congrats on publishing your design system doc site! You can now take your site and customize it for your design system.

* Read more about how to customize a Nextra doc site here:[  https://nextra.vercel.app/themes/docs/configuration](https://nextra.vercel.app/themes/docs/configuration)
* You can adjust the side nav display names and order using meta.json files.[  Check out the Nextra repo for an example](https://github.com/shuding/nextra/blob/main/pages/meta.json). Meta files can be edited with Gist as long as when you type "you then press backspace so it becomes JSON acceptable
* Connect your site to a custom domain by going to your Vercel project settings > Domains and adding your domain details.

### Done!

Once you've added your documentation and customized your site to your liking be sure to share it with your team and if you want, the world! I would be glad to see your sites on my Twitter:[  @mk_wlsn](https://twitter.com/mk_wlsn)