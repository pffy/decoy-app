# decoy-app
this is a humble Google App Engine tutorial repo

## REQUIRED READING
  + SKIM THIS: 
    + https://derechodelared.com/wp-content/uploads/2021/03/Google-Cloud-Developers-Cheat-Sheet.pdf
  + EXPLORE THIS: 
    + https://github.com/priyankavergadia/google-cloud-4-words
  + READ THIS: 
    + https://cloud.google.com/sdk/docs/images/gcloud-cheat-sheet.pdf
    + https://cloud.google.com/billing/docs/concepts

## OVERVIEW

In this exercise, you will notice that we will not visit the Google Cloud Console web site. 

Instead, we will be staging and deploying our simple project from the command-line interface (CLI).

The Google Cloud CLI allows us to more efficiently manage and deploy Google Cloud Platform (GCP) resources without navigating the web user interface (UI).

This is a very useful skill for timely and precise GCP resource management, as the web UI may be a more cumbersome way to simply flip switches. 

The Google Cloud CLI also enables us to create automated shell scripts (in later lessons), with little or no human interaction. These scripts can provide a versatile template for building and deploying many projects for multiple users.

In the following step-by-step tutorial, we will use Google web-based tools to:

  * Create a project workspace in your home directory
  * Clone a project template from GitHub
  * Create a new GCP project
  * Add billing informoation to that new GCP project
  * Enable GCP Cloud Build (after adding required billing info)
  * Deploy the project files to App Engine

  
## STEPS

1. First, we open the Google Cloud Shell (Terminal only) in your web browser:
  
    + https://shell.cloud.google.com/?show=terminal
      + Ctrl + Click to open in a new tab
      + Shift + Click to open in a new window

> **NOTE:** `gcloud` and `git` are already installed. Sweet!

> **NOTE:** If you prefer, you can change the terminal text size to be very, very big.


2. Next, we create a new folder in your home directory using the following bash commends:


```bash
$ cd ~
$ mkdir foo
```

3. Then, we change the working directory to the new folder:

```bash
$ cd foo
```

4. In the new folder `~/foo`, we clone the `decoy-app` repository from GitHub and change the working directory again as follows:

```bash
$ git clone https://github.com/pffy/decoy-app
$ cd decoy-app
```

We are now in the folder `~/foo/decoy-app`.

5. Before we continue, we authenticate.
```bash
$ gcloud init
```

6. **Create a new project.** Enter the new project name when prompted.

7. Find the billing account we created in an earlier lesson:

```bash
$ gcloud beta billing accounts list
```

8. Link that billing account to your new project.

```bash
$ gcloud beta billing projects link [YOUR_PROJECT_ID] 0X0X0X-0X0X0X-0X0X0X
```

9. In order to deploy the project to App Engine, we must enable the Cloud Build API:

```bash
$ gcloud services enable cloudbuild.googleapis.com
```

10. Now, we can deploy your first app. Be sure to choose a server location.

```bash
$ gcloud app deploy
```

11. After your project is deployed to App Engine, we can check your project web site.
```bash
$ gcloud app browse
```

Alternatively, you can simply visit the following URL in your web browser.
```bash
GO TO URL: https://[YOUR_PROJECT_ID].appspot.com
```

This step-by-step tutorial required some human interaction. Now, we will discuss some options for more automation using the GCP CLI.

## More Automation

Automation allows you to do more with little or no human interaction. 

In the above tutorial, we were tasked with the following human interactions:

  * Create a new project ID
  * Choose a region (location) for your App Engine application
  * Deploy the application to App Engine

For each task, we were provided a prompt, where we provided additional input. 

However, all these tasks can be automated without the prompts or human interaction.

For example, when we simply want something done by a `gcloud` command without prompts, you can use the `-q` global flag (`--quiet`).

It is possible for us to create a new project from the CLI, using the following command:

```
$ gcloud projects create new-project-id-here -q
```

It is also possible to initialize your newly-created Google App Engine application using the following command:

```
$ gcloud app create --region us-west2 -q
```

> **NOTE:** You can use any available region. `us-west2` was used an example.

> **NOTE**: Remember, you must assign a billing account ***and*** enable Cloud Build prior to deploying the App Engine application.

Once your App Engine application is initialized, you can simply deploy it from the application root folder with the `app.yaml` file:

```
$ gcloud app deploy -q
```

Pretty cool, huh!

We discussed this additional automation as a preview of what is possible with the Google Cloud Plaform CLI.

At this point, the extra commands in this section are optional, but they show human interaction can be minimized for better productivity.

In later lessons, we will implement more shell scritping with less human interaction and more flexibility.

## Conclusion

still TBD
