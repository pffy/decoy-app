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

  * item
  * item
  * item
  * item
  * item 
  
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

4. In the new folder, we clone the `decoy-app` repository from GitHub and change the working directory again as follows:

```bash
$ git clone https://github.com/pffy/decoy-app
$ cd decoy-app
```

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

## Conclusion

TBD
