# decoy-app
this is a humble Google App Engine tutorial repo

## REQUIRED READING
  + TBD
  + TBD
  + TBD

## OVERVIEW

In this exercise, you will notice that we will not visit the Google Cloud Console web site. Instead, we will be staging and deploying our simple project from the command-line interface (CLI).

This is a very useful skill for timely cloud resource management. It also allows us to create automated shell scripts in later lessons, with little or no human interaction.

## STEPS

1. Open Google Cloud Shell (Terminal only).
  
    + https://shell.cloud.google.com/?show=terminal
      + Ctrl + Click to open in a new tab
      + Shift + Click to open in a new window

> **NOTE:** `gcloud` and `git` are already installed. Sweet!

> **NOTE:** If you prefer, you can change the text size to be very, very big.


2. Create new folder in home directory:
```bash
$ cd ~
$ mkdir foo
```

3. Change the directory to the folder:
```bash
$ cd foo
```

4. Clone the decoy repo:
```bash
$ git clone https://github.com/pffy/decoy-app
$ cd decoy-app
```

5. Authenticate.
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

9. Enable the Cloud Build API.
```bash
$ gcloud services enable cloudbuild.googleapis.com
```

19. Deploy your first app. Choose the server location.
```bash
$ gcloud app deploy
```

11. Check your project web site.
```bash
$ gcloud app browse
```

OR:
```bash
GO TO URL: https://[YOUR_PROJECT_ID].appspot.com
```
