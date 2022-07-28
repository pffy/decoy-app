# decoy-app
this is a humble Google App Engine tutorial repo

## REQUIRED READING
  + TBD
  + TBD
  + TBD

## STEPS

1. Open Google Cloud Shell (Terminal only).
  
    + CLICK: https://shell.cloud.google.com/?show=terminal

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
```

5. Authenticate.
```bash
$ gcloud init
```

6. Create a new project.

You can create a new project when prompted.

If you are already authenticated, you simply type the following:
```bash
$ gcloud app create --project=[YOUR_PROJECT_ID]
```

7. Enable the Cloud Build API.
```bash
$ gcloud services enable cloudbuild.googleapis.com
```

8. Deploy your first app. Choose server location.
```bash
$ gcloud app deploy
```

9. Check your project web site.
```bash
$ gcloud app browse
```

OR:
```bash
GO TO URL: https://[YOUR_PROJECT_ID].appspot.com
```
