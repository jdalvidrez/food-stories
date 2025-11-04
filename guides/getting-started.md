---
layout: base
title: Getting Starting with Xanthan
subtitle: A preliminary guide to sustainable and extensible project websites
author: Fred Gibbs
date: 2019-10-03
---

# {{page.title}}
This page specifies each step necessary to get started with your own website. You can finish these steps and **have your own website in about 10 minutes**.

### Create an account at GitHub
- Create an account at [GitHub](http://github.com/register). Whatever username you choose will be referred to below as GITHUB_USERNAME.
- Once you've gone through the confirmation process, make sure you are at your account home page. The URL will look like http://github.com/GITHUB_USERNAME.


### Make a copy of Xanthan
Rather than create everything from scratch, let's start with a basic set of core files for your site. Our basic template is called Xanthan (like the gum), because it holds everything together.
- Go to the [Xanthan repository](http://github.com/amaranth-unm/xanthan)
- Click the green `Use this Template` button in the upper right.
- Name your repository (referred to as REPOSITORY below). You don't need to call it `xanthan`, and you can always rename it later (or delete it and start over).
- Click the green `Create Repository` button in the lower right.

### Confirm your config file
If you named your repository something other than `xanthan`, you need to make one small configuration edit. If you did not change `xanthan` to something else, skip this section.
- Click the `Code` tab near the top left
- Edit `_config.yml` file to have the same `baseurl` as your repository name. 
- Commit your change with the green Commit button.

### Enable GitHub Pages
Now that your have your starter files, we just need to tell GitHub that you want to use your repository to build a website.
- Click on the `Settings` tab in the upper right of the nav bar. 
- On the left, click the link for `Pages`.
- Near the top, under the Build & Deployment section, under `Source`, the `Deploy from a Branch` should be selected.
- Directly below, under `Branch`, change from `None` to `main`.
- Click the `Save` button that appears on that same line.
- Your site is now being built, and you can see the status via the `Actions` tab.
- After about a minute, reload the page and you'll see a link to your site.  
- The URL that appears there looks like: http://GIHUB_USERNAME.github.io/REPOSITORY/. For example, your final URL should loook like http://fredgibbs.github.io/xanthan


### Congratualtions! 
You have a website! 

Now you're ready the explore the components of your site and start editing. Let's start with [Understanding Folders](understanding-folders).