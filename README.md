# SFDX-Project-Template

This guide helps Salesforce developers get started with GitLab and Salesforce Devlopment quickly including details on devlopment models, setting up CI/CD with GitLab pipelines, and how to deploy your final changes to production

# Part 1: Importing Project Templates

To use this project template for a new [GitLab Project](https://docs.gitlab.com/ee/user/project/) follow the steps below: 

### Step 1

Login to [Gitlab.com](https://gitlab.com/users/sign_in) and navigate to the [projects tab](https://gitlab.com/dashboard/projects) at the top. 

![Login to GitLab.com](./imgs/login.png)

### Step 2

Click on 'Projects' and then 'Your Projects' in the top navigation drop down pane. 

![New project nav](./imgs/project-nav.png) 

Now click the [**New Project**](https://gitlab.com/projects/new) green button to create a new project. 

![Create a new Project button](./imgs/new-project-button.png)

### Step 3 

Navigate to **Import Project** at the top of the page. Then click the **git Repo by URL** button. 

Enter in [this project's](https://gitlab.com/sfdx/sfdx-project-template/tree/master) git URL : [https://gitlab.com/sfdx/sfdx-project-template.git](https://gitlab.com/sfdx/sfdx-project-template.git) in the `Git repository URL` form field. 

![Import by git Repo URL](./imgs/new-project.png)

### Step 4

Give your project a name and optionally a description to get started. Finally after confirming your **Visibility Level** for your new project, click the **Create Project** green button to initiate. 

![Initializing Project](./imgs/new-project-2.png)

After completing the steps above, you'll have a new project initialized under your GitLab account.

## Part 2: Choosing a Development Model

There are two types of developer processes or models at Salesforce. These models are explained below. Each model offers pros and cons and is fully supported.

### Package Development Model

The package development model allows you to create self-contained applications or libraries that are deployed to your org as a single package. These packages are typically developed against source-tracked orgs called scratch orgs. This development model is geared toward a more modern type of software development process that uses org source tracking, source control, and continuous integration and deployment.

If you are starting a new project, we recommend that you consider the package development model. For details about the model, see the [Package Development Model](https://trailhead.salesforce.com/en/content/learn/modules/sfdx_dev_model) Trailhead module.

When working with source-tracked orgs, use the commands `SFDX: Push Source to Org` (VS Code) or `sfdx force:source:push` (Salesforce CLI) and `SFDX: Pull Source from Org` (VS Code) or `sfdx force:source:pull` (Salesforce CLI). Do not use the `Retrieve` and `Deploy` commands with scratch orgs.

### Org Development Model

The org development model allows you to connect directly to a non-source-tracked org (sandbox, Developer Edition (DE) org, Trailhead Playground, or even a production org) to retrieve and deploy code directly. This model is similar to the type of development you have done in the past using tools such as Force.com IDE or MavensMate.

For details about the model, see the [Org Development Model](https://trailhead.salesforce.com/content/learn/modules/org-development-model) Trailhead module.

If you are developing against non-source-tracked orgs, use the command `SFDX: Create Project with Manifest` (VS Code) or `sfdx force:project:create --manifest` (Salesforce CLI) to create your project. If you used another command, you might want to start over with this command to create a Salesforce DX project.

When working with non-source-tracked orgs, use the commands `SFDX: Deploy Source to Org` (VS Code) or `sfdx force:source:deploy` (Salesforce CLI) and `SFDX: Retrieve Source from Org` (VS Code) or `sfdx force:source:retrieve` (Salesforce CLI). The `Push` and `Pull` commands work only on orgs with source tracking (scratch orgs).

This Project Template uses the Package Development Model

## The `sfdx-project.json` File

The `sfdx-project.json` file contains useful configuration information for your project. See [Salesforce DX Project Configuration](https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev/sfdx_dev_ws_config.htm) in the _Salesforce DX Developer Guide_ for details about this file.

The most important parts of this file for getting started are the `sfdcLoginUrl` and `packageDirectories` properties.

The `sfdcLoginUrl` specifies the default login URL to use when authorizing an org.

The `packageDirectories` filepath tells VS Code and Salesforce CLI where the metadata files for your project are stored. You need at least one package directory set in your file. The default setting is shown below. If you set the value of the `packageDirectories` property called `path` to `force-app`, by default your metadata goes in the `force-app` directory. If you want to change that directory to something like `src`, simply change the `path` value and make sure the directory you’re pointing to exists.

```json
"packageDirectories" : [
    {
      "path": "force-app",
      "default": true
    }
]
```

## Part 3: Making changes

To Start working you will need to create a branch and clone your repositry locally 

## Part 4: Setting up GitLab Pipelines



## Part 5: Deploying to Production

Deploy your changes to production using [packaging](https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev/sfdx_dev_dev2gp.htm) 

