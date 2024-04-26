# hugo-mock-landing-page

This repository includes a workflow allowing the website created in the previous homework to be deployed. 
Below was obtained using Claude:
The included YAML file plays a crucial role in the deployment process of a Hugo website to GitHub Pages. Here's how it contributes to the deployment:
Workflow Trigger: The on section specifies that the workflow will be triggered whenever there is a push event to the main branch of the repository. This means that whenever new changes are pushed to the main branch, the deployment process will automatically start.
Checking Out Code: The first step in the deploy job is to check out the source code repository using the actions/checkout action. This ensures that the latest code is available for building the Hugo website.
Hugo Environment Setup: The next step initializes the Hugo environment using the peaceiris/actions-hugo action. This action sets up the specified version of Hugo (0.123.4) and enables the extended features required for building the website.
Building Static Files: The hugo -D --gc --minify command is executed to build the static files for the website. The -D flag includes draft content, --gc enables garbage collection, and --minify minifies the output files for better performance.
GitHub Pages Deployment: After building the static files, the peaceiris/actions-gh-pages action is used to deploy the compiled website to the gh-pages branch of the repository. This branch is treated as a special branch by GitHub Pages, and any content pushed to it will be served as a website hosted on GitHub Pages.
Authentication and Commit Details: The deployment process uses the GITHUB_TOKEN secret to authenticate with GitHub and push the changes to the gh-pages branch. The user_name and user_email parameters specify the commit author details for the deployment commit.
Custom Domain Setup (Optional): The YAML file includes a commented section for specifying a custom domain (cname) if you want to use a custom domain for your GitHub Pages website instead of the default username.github.io URL.
