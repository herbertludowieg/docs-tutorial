# Tutorial on creating documentation to publish on GitHub Pages

**Disclaimer**: this is based purely on the knowledge that I have gathered through the years. I am in no way an expert on how to do this. A lot of what you'll see here are things that I have personally done and should serve as a beginner guide.

GitHub has a service for open source projects where you can host
documentation pages for your code base called GitHub pages. Enabling this
service allows the maintainers to automatically build the documentation pages in HTML or Markdown format. This is a step-by-step tutorial that will walk you through how to do this for three cases:

- Pure HTML
- Pure Markdown
- reStructured text converted into HTML

In the first case for pure HTML code it is very simple as there is not conversion that has to happen to publish to an HTML website (I use this on my personal portfolio website). This can give you the most control over how your website/documentation looks, but requires the greatest amount of work, obviously. Using pure Markdown is a very convenient option as it is simple to create pages, very simplistic, and easy to maintain. However, this can be very restrictive in terms of how the final product will look. Using reStructured text is similar to how you would write things in Markdown, but it is very simple to use third-party programs like [Sphinx](https://www.sphinx-doc.org/en/master/) to compile the files into HTML. Some third party programs, like Sphinx, can also go through your source code and, as long as the formatting is correct, they can automatically build the documentation for the source code (I use this a Python code that I have created).

**Note**: I am assuming that you are creating the documentation pages for a repository, not a personal website to be hosted with the hostname `https://username.github.io`. If you are trying to create a personal website, you will need to create a repository with the name `username.github.io`, where `username` in both cases is your GitHub username. I will highlight where there may be some slight differences in the information provided here, but the only difference is the web address used for the website.

## Enabling GitHub pages on the repository

First thing you want to do is go to the "Settings" tab in the repository

![image](images/main-page-sel-set.png)

Then you want to go into the "Pages" tab

![image](images/settings-sel-page.png)

If you have not set up the GitHub pages you will see

![image](images/settings-pages.png)

For this tutorial I will only be talking about how to do this when source is left as the default "Deploy from a branch". There is a drop down menu to select which branch you want to deploy from

![image](images/build-and-deploy-branch.png)

Once you select it, there will be an additional drop down to select which directory to build the deployed pages from as

![image](images/build-and-deploy-sel-dir.png)

In this tutorial we will go through the following combinations:

- Build from `main` branch from `/(root)` directory

- Build from `main` branch from `/docs` directory

- Build from `gh-pages` branch from `/(root)` directory. I just arbitrarily use the `gh-pages` branch as I usually reserve it for when I build the documentation with Sphinx and do a force push to this branch (more on this later).

Once you select the branch and directory (for now just do it as `main` branch and `/(root)` directory) you want to go ahead and hit "Save". This will trigger a workflow build "pages-build-deployment" in the "Actions" tab

![image](images/main-page-sel-actions.png)

You will now see

![images](images/actions-build.png)

Once the orange dot turns into a solid green check as

![image](images/actions-build-deploy-comp.png)

The page should have been deployed with the contents of the `README.md` file being displayed on the website that was created. Typically the web address will be `https://username.github.io/repo-name`, where `username` is your GitHub username and `repo-name` is the name of the repository. Here, there can be a small difference in what you may be doing. If this is your personal website such that `repo-name` is `username.github.io`, the web address is just `https://username.github.io`. You can find where the pages are hosted in the GitHub pages settings seen here

![image](images/settings-pages-deployed.png)


