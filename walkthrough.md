
# DevOps UX Product Tutorial

[Codelab Feedback](https://github.com/googlecodelabs/devops-ux-tutorial/issues)


## Introduction




This tutorial is a simplified developer workflow meant to familiarize users with Cloud Source Repositories (CSR), Cloud Code Review (CCR) and Cloud Build Triggers. 

### __What you will build__

You'll be creating a new code repository and editing files in an existing Google Cloud project that has been configured to work with Cloud Source Repositories, Cloud Code Review and Cloud Build triggers. In order to showcase the tools in action your repo will be published using App Engine as an internally viewable  [static website](http://ricewing.googleplex.com). Note that while you will be editing source files, no prior coding experience is needed as all the sample code and instructions will be provided.

### __What you'll learn __

* How to create a Cloud Source Repository in an existing Cloud Project.
* How to publish a simple website via App Engine.
* How to enable and setup Cloud Build triggers to automatically publish your site.
* How to configure your repository to use Cloud Code Review to manage changes to review and submit changes to code.
* How to use Cloud Code Review to see the history of changes in your code.

### __What you'll need__

* You must be a member of  [di-ux@google.com](mailto:di-ux@google.com) to access to the necessary GCP project.
* You should have a text editor or IDE for editing files.
* You should be comfortable using basic  [terminal commands](https://lifehacker.com/5633909/who-needs-a-mouse-learn-to-use-the-command-line-for-almost-anything) (`ls`, `cd`, etc.).
* You should have a basic understanding of Git and be comfortable using common  [git commands](https://hackernoon.com/understanding-git-fcffd87c15a3) (`add`, `commit`, `push`, etc.).
* Basic knowledge of HTML and CSS is not required, but can be useful.

### __Questions?__

If you have questions, or need assistance with the tutorial, please reach out to Ric Ewing ( [ricewing@](https://moma.corp.google.com/person/ricewing)). 


## Prework: getting set up

*Duration is 5 min*


Before we get to the tutorial, there are a few tasks to complete first. 

You will need to:

* Verify that you can access the tutorial GCP Project.
* Verify access to Cloud Code Review or get whitelisted.

### __Verify project access__

As a member of di-ux@, you should have access to the GCP project "devops-ux-sandbox" which is used for this tutorial. Go to Pantheon and try switching to the  [devops-ux-sandbox](https://pantheon.corp.google.com/home/dashboard?project=google.com:devops-ux-sandbox) project.

![6q854kYPxXXx2WsSQAtCejXBOmaHElQ6AQ_JRXzo9lovVExe9dQWZZBRG4jPHE04tS-L1Ndaw_xUTnxALdBncX_7jCUx73MoEp6Xz2GXWrZ4_taMF-pOlcRCFnhLyRZ_pNyCufm2](https://lh6.googleusercontent.com/6q854kYPxXXx2WsSQAtCejXBOmaHElQ6AQ_JRXzo9lovVExe9dQWZZBRG4jPHE04tS-L1Ndaw_xUTnxALdBncX_7jCUx73MoEp6Xz2GXWrZ4_taMF-pOlcRCFnhLyRZ_pNyCufm2)

If you can access the devops-ux-sandbox project, you're all set, if not you will need to contact  [ricewing@](http://teams/ricewing@) to request access to the project.

### __Verify access to Cloud Code Review__

Because Cloud Code Review isn't publicly available yet, you'll need to get access to it by adding yourself to the Google Group  [g/cloud-source-tools-cr-eap](https://g.corp.google.com/cloud-source-tools-cr-eap). This group serves as a whitelist that allows you to see the Code Review features in the UI.

Once you've added yourself to the group, go to  [https://source.cloud.google.com/](https://source.cloud.google.com/) and make sure the Code Review menu item appears in the left hand nav.

![whZgHvxsaK-7YgDmt4ufyU8vTABsizNMExHIIny21v2u_BDIgVwBI3oCAaGf2pVGVKmcfoexp7z4jujxWOOw-R5sF25ZkWt3e4WNT4nHWecq7RLLAVBQnDadgjM3eEVJ8VoZz8zQ](https://lh6.googleusercontent.com/whZgHvxsaK-7YgDmt4ufyU8vTABsizNMExHIIny21v2u_BDIgVwBI3oCAaGf2pVGVKmcfoexp7z4jujxWOOw-R5sF25ZkWt3e4WNT4nHWecq7RLLAVBQnDadgjM3eEVJ8VoZz8zQ) 


## Create your repository

*Duration is 3 min*


You'll be creating a new repository within the devops-ux-sandbox project, so go to  [https://source.cloud.google.com/](https://source.cloud.google.com/) and click on the "New Repository" button in the top left of the page.

![w-TNvgPgqrGXBv2b29N8kAHcIj1sxhtUXf0uGSixsM1uwEp-sJMbnMYM_-RK_2UupxvYtkETxI0z1pBetKlXnLpErulpN7MTCOD9TqTa3Gzz_y5mjfXNMogyUQMqieMZ4sGeEVrB](https://lh5.googleusercontent.com/w-TNvgPgqrGXBv2b29N8kAHcIj1sxhtUXf0uGSixsM1uwEp-sJMbnMYM_-RK_2UupxvYtkETxI0z1pBetKlXnLpErulpN7MTCOD9TqTa3Gzz_y5mjfXNMogyUQMqieMZ4sGeEVrB)

Select "Create new repository" in the dialog and click "Continue".

![Q7ZyVJAQF2eVGmGUJ-QcgbvZ9JzriW0jjmKLCfgB3qsvZxyccAUa5r_kNAfm5Pn3WyufTEjT2_2G9DzfA2bsLjYZfF6zMktTaVRV26U_tXdRpQz0lu7V17EYovvacbuLZ8M3mYlF](https://lh4.googleusercontent.com/Q7ZyVJAQF2eVGmGUJ-QcgbvZ9JzriW0jjmKLCfgB3qsvZxyccAUa5r_kNAfm5Pn3WyufTEjT2_2G9DzfA2bsLjYZfF6zMktTaVRV26U_tXdRpQz0lu7V17EYovvacbuLZ8M3mYlF)

You'll need to enter a __unique name__ for your repository, and because you're working in a shared project we recommend using your __username__ to make it easier to locate.

Make sure to the project is "google.com:devops-ux-sandbox", and then click the "Create" button.

![A1gYxZTuqbTRz69FdJ2ReUFzJ7bcl-396P8vDUT8TBIlQEMLR7BlUdWtt5uIUfBjJjy-taRswIEJVLt-z6GBt1mhUpjQq3G7UUmR33cW073YSCpJy0ixl60FlN5Mbb07QwXug8qJ](https://lh4.googleusercontent.com/A1gYxZTuqbTRz69FdJ2ReUFzJ7bcl-396P8vDUT8TBIlQEMLR7BlUdWtt5uIUfBjJjy-taRswIEJVLt-z6GBt1mhUpjQq3G7UUmR33cW073YSCpJy0ixl60FlN5Mbb07QwXug8qJ)

You now have a brand new repository! 

You should see a dialog with instructions on how to add code to it, but __don't follow those directions yet__. That will happen in the next step, cloning your repository.

![XWSq08MxZ1lI6Ke5bmxY5OpRt3rzxC4wdvWmqK6v7KgtUFJM-A6-VGJIrhsMJr9t3HflfDMajKhPT9OlYJR-Yuhok0KwRM_yeHpXg7JKzgdvOQZecgO8EFJWPyiTLfQsLLYO0D6Y](https://lh3.googleusercontent.com/XWSq08MxZ1lI6Ke5bmxY5OpRt3rzxC4wdvWmqK6v7KgtUFJM-A6-VGJIrhsMJr9t3HflfDMajKhPT9OlYJR-Yuhok0KwRM_yeHpXg7JKzgdvOQZecgO8EFJWPyiTLfQsLLYO0D6Y)


## Cloning your repository

*Duration is 5 min*


If the previous step was successful, you should see the following dialog on the Cloud Source Repositories page:

![XWSq08MxZ1lI6Ke5bmxY5OpRt3rzxC4wdvWmqK6v7KgtUFJM-A6-VGJIrhsMJr9t3HflfDMajKhPT9OlYJR-Yuhok0KwRM_yeHpXg7JKzgdvOQZecgO8EFJWPyiTLfQsLLYO0D6Y](https://lh3.googleusercontent.com/XWSq08MxZ1lI6Ke5bmxY5OpRt3rzxC4wdvWmqK6v7KgtUFJM-A6-VGJIrhsMJr9t3HflfDMajKhPT9OlYJR-Yuhok0KwRM_yeHpXg7JKzgdvOQZecgO8EFJWPyiTLfQsLLYO0D6Y)

This dialog appears when you have successfully created a new repository, but haven't yet added anything to it. Because you're going to start a repository from scratch, choose "Clone your repository to a local Git repository" under how to push code to the repository. You'll be using the  [gcloud command line tool](https://cloud.google.com/sdk/) to manage authentication, so choose "Google Cloud SDK" for the authentication method. Setting these options will show the correct directions for cloning your repository to your local machine.

### __Verify that gcloud command line is installed__

In order to clone the repository you will need to have the gcloud command line tool installed. To check if you have it installed and configured correctly, open terminal and enter the following command:

    gcloud config list

If gcloud command line tools are installed, you should see something similar to the following.

    $ gcloud config list
    [core]
    account = username@google.com
    disable_usage_reporting = False
    project = google.com:devops-ux-sandbox

If your config shows that project is not `google.com:devops-ux-sandbox`, enter the following command in terminal to update the config to point at the correct project.

    gcloud config set project google.com:devops-ux-sandbox

At this point, you should be ready to clone your repository.

### __Creating a local clone__

Choose a directory on your machine to clone your remote repository into. "Cloning" a repository creates a copy of it on your computer, referred to as a "local repository". This is where you'll add or edit files, "commit" those changes and then "push" them to the remote repository. 

In terminal `cd` into the directory where you want to create the repository and __follow steps 3 and 4 __from the above dialog. 

You now have a local clone of your repository, the next step is to add files to it.


## Adding code to your repository

*Duration is 5 min*


To reduce the need to write code for this tutorial, there is a zip file of all the necessary files you'll need. 

[](https://drive.google.com/open?id=1hvUZPqh6kYvxHgW3qk3Iu70oMgZTj1D3)

Place the `devops_tutorial.zip` file into your repository directory. Open terminal, `cd` into your repository if you aren't already there, and enter the following command to unzip the contents into the repository.

    unzip devops_tutorial.zip -d .

The `unzip` command above creates the following files in your local repository:

* The `www` directory, which contains the code for a simple single page website.
* A `README.md` file, used to display useful information about your repository for other developers and shown by default in Cloud Source Repository.
* The App Engine `app.yaml` file used to define the App Engine settings for your site.
* The  `cloudbuild.yaml` which contains the deploy instructions used by Cloud Build.
* A hidden file, `.gitignore` which is used to control which files are tracked for changes.

### __The initial commit__

You now have a local repository with a lot of new files. Because the repository is being managed by Git, these new files are marked as changes. To check the status of your repository, you can use the `git status` command. You should see something similar to the following.

    $ git status
    
    On branch master
    
    No commits yet
    
    Untracked files:
      (use "git add <file>..." to include in what will be committed)
    
            .gitignore
            README.md
            app.yaml
            cloudbuild.yaml
            devops-tutorial.zip
            www/
    
    nothing added to commit but untracked files present (use "git add" to track)

To stage these local changes to the " commit". To do this, the `git add` command is used. 

    git add .

The `.` in the above command is a shortcut to stage all available changes, in this case all the new files you've added to the repository. This updates the staged commit with any changed, deleted or new files. If you're curious about what changes were added you can use `git status` to see what's been staged. 

When you're ready to commit the changes, your next command is:

    git commit -m 'initial commit'

This commits the changes to your local repository with a description of "initial commit". You can think of a commit as a "snapshot" of the files in your repository. Each commit is visible as part of your repository's history, so a meaningful description is useful. Note that commits are only on your local repository, not the remote. This allows you to work locally, keeping snapshots as you go, until you're ready to push your changes to the remote repository.

At this point you've added and commited files to start your local repository, so you're ready to update the remote repository. The `git push` command is used to update remote repositories.

    git push -u origin master

This updates the remote repository to match the commits to your local repository. Go back to the Cloud Source Repositories page and refresh it to see your files in Cloud Source Repository.

![OA3YBd287PFYz8255SMDpU3ZCS9iIpIbwicOGlzQlOMWx9vnPPIucb3qdoZvqnk1NEJyiy-jcnyUEywhIVQXyerfZViSU_6xGSNGkx6higx9iNeGnW_4xwTifIyaA_MesKUD2_pK](https://lh6.googleusercontent.com/OA3YBd287PFYz8255SMDpU3ZCS9iIpIbwicOGlzQlOMWx9vnPPIucb3qdoZvqnk1NEJyiy-jcnyUEywhIVQXyerfZViSU_6xGSNGkx6higx9iNeGnW_4xwTifIyaA_MesKUD2_pK)

You're all set with Cloud Source Repository! 


## Cloud Source Repository tour

*Duration is 5 min*


![OA3YBd287PFYz8255SMDpU3ZCS9iIpIbwicOGlzQlOMWx9vnPPIucb3qdoZvqnk1NEJyiy-jcnyUEywhIVQXyerfZViSU_6xGSNGkx6higx9iNeGnW_4xwTifIyaA_MesKUD2_pK](https://lh6.googleusercontent.com/OA3YBd287PFYz8255SMDpU3ZCS9iIpIbwicOGlzQlOMWx9vnPPIucb3qdoZvqnk1NEJyiy-jcnyUEywhIVQXyerfZViSU_6xGSNGkx6higx9iNeGnW_4xwTifIyaA_MesKUD2_pK)

[TODO: add a quick tour of CSR features]


## Publish your website with App Engine

*Duration is 5 min*


Now that you have populated your repository with code, you can test out publishing your site. You'll do this via hosting it on App Engine. 

App Engine looks for a file `app.yaml` for instructions on how to host your web app. As part of the sample code you already have this file, and it's configured to host a simple website. 

To publish your site, enter the following command in terminal, __replacing "username" with the name of your repository__. 

    gcloud app deploy --no-promote --version username

When asked if you want to continue, enter `Y` and you'll see the progress on your site being published. Look for the following line to see the URL for your site (it will be based on your repository name).

    Deployed service [default] to [https://username-dot-devops-ux-sandbox.googleplex.com]

Following that URL you should see your website. 

![ZRm590oMKsCzjLziRs2o2yS5S4zLMUey3BJp7GjS056ESoJmqPyHpgPslaH3bqjK26L6SKtw7HegXC8qH6FHP_P6xoXpaxV1BugIxJclymZeUUoBAcA8gZlLJvSYAGRZuHuCnzLF](https://lh3.googleusercontent.com/ZRm590oMKsCzjLziRs2o2yS5S4zLMUey3BJp7GjS056ESoJmqPyHpgPslaH3bqjK26L6SKtw7HegXC8qH6FHP_P6xoXpaxV1BugIxJclymZeUUoBAcA8gZlLJvSYAGRZuHuCnzLF)

Leave this tab open, as it will be convenient to check on builds.


## Setting up Cloud Build Triggers

*Duration is 5 min*


Cloud Build Triggers watch for events in your repository, and then perform a set of actions. You're going to set up a Build Trigger to watch the master branch of the repository for changes and then automatically deploy the site.

### __Editing cloudbuild.yaml__

Before you set up a trigger, there's a file in your repository, `cloudbuild.yaml`, that is used by Cloud Build that your need to modify. The file is really just a list of commands to be executed when a build trigger is activated. In this case there are two steps, a "gcloud app deploy" command which is the same one you manually entered before to have App Engine publish your website, and "gcloud app describe" which lists out information about the service (used for debugging). That first command needs an update to work with this tutorial.

Open `cloudbuild.yaml` and change line 3, replacing "username" with the name of your repository and save it. This will change where App Engine will deploy your website so that it won't conflict with others in the devops-ux-sandbox project. 

In order for Cloud Build to access these changes, they need to be pushed to the remote repository, so stage and commit them...

    git add .

    git commit -m 'updated cloudbuild.yaml'

...then push them to the remote.

    git push origin master

Now you're ready to set up a build trigger.

### __Configuring Build Trigger__

Cloud Build is located in GCP, so click on the "Cloud Console" button at the top of the Cloud Code Review page to get back to Pantheon. In the GCP menu, find Cloud Build in the Tools section, and click on Build triggers.

![uAgEfYhaDPDu0RCIC5iJEqSzRNMoJ2wKYJe-zOyzlClgCv_OsH_kqxJ7x2NupHXnk9k7xLf8kJDkZnyK1WWq-2aSpWYnBnBxaiz9eEVyBEBwrwQra_gq2xUNShT6tQ-nVETaCn8v](https://lh4.googleusercontent.com/uAgEfYhaDPDu0RCIC5iJEqSzRNMoJ2wKYJe-zOyzlClgCv_OsH_kqxJ7x2NupHXnk9k7xLf8kJDkZnyK1WWq-2aSpWYnBnBxaiz9eEVyBEBwrwQra_gq2xUNShT6tQ-nVETaCn8v)

### __Creating a trigger__

You may need to enable the Cloud Build API, so if prompted, click on the "Enable Cloud Build API" Button.

If you haven't set up a build trigger before, you'll be prompted to "Create trigger". Otherwise, click "Add trigger" at the top of your build triggers page. Either case, you should end up at a three step flow for creating a trigger. 

![5V_W9aHQPRGC-oGpjqa6i544YJF0ScbLnbJrJwd26HSTAelqXAdvPin7rOTlHCSHI6u4dzt8ssN2EWEdl3Utifp3VchAsUwn-4kED7-Zy9ehf2qETfUveula-Pn1Cps9p11qE59R](https://lh6.googleusercontent.com/5V_W9aHQPRGC-oGpjqa6i544YJF0ScbLnbJrJwd26HSTAelqXAdvPin7rOTlHCSHI6u4dzt8ssN2EWEdl3Utifp3VchAsUwn-4kED7-Zy9ehf2qETfUveula-Pn1Cps9p11qE59R)

In the first step of the Create trigger flow, choose "Cloud Source Repository" as the host and click "Continue".

![Vn4ptThVCllrQ8EHE7pjPW8UW1zHEMpT8hjWrLlHAJfsWmS9IJOH1Lkc_rZh3glnD8DArfB26NNyfnzvRf8c3KcpKifNFn8ypiiFcwogY65l3hPAMg-Sy9TIev9zIjoFDkj65WKO](https://lh6.googleusercontent.com/Vn4ptThVCllrQ8EHE7pjPW8UW1zHEMpT8hjWrLlHAJfsWmS9IJOH1Lkc_rZh3glnD8DArfB26NNyfnzvRf8c3KcpKifNFn8ypiiFcwogY65l3hPAMg-Sy9TIev9zIjoFDkj65WKO)

In step 2, select your repository from the list, and click "Continue"

![P7r3JzVBLb44tjgSb_lDCJpbjaHJfj7ZYuh2rohy62Bs7pu-jPEpQJaXWWe-Wo9qfgp0nJ641dpSiTHiAU9I-Mh0w_y_rLHWTqjvnXrpZAI2YbWFM9GHjAkv4cElTb440Kgedz7T](https://lh3.googleusercontent.com/P7r3JzVBLb44tjgSb_lDCJpbjaHJfj7ZYuh2rohy62Bs7pu-jPEpQJaXWWe-Wo9qfgp0nJ641dpSiTHiAU9I-Mh0w_y_rLHWTqjvnXrpZAI2YbWFM9GHjAkv4cElTb440Kgedz7T)

In step 3, set your Branch to "master" and select "cloudbuild.yaml" as your Build configuration. The "cloudbuild.yaml" file is where you'll set the commands you want the trigger to perform. You already have this file in your repository because it was part of the sample code provided, but it will need a modification before we can run a build. We'll get to that in a moment, so for now just click on "Create trigger" and you should be taken to your Build triggers screen.

![spdMtod8q9s5xsuH4V5hPapMYzJpOaAzi3ZbJUn_fvYsh1CavfmKG-uxITq3XhajubneQZhW6xY7kYUjgBAm5ZuR0nHkwYw9__39uBKYs_eTa-Pfb7vhCwuybqQeGs9JgN0vFur1](https://lh5.googleusercontent.com/spdMtod8q9s5xsuH4V5hPapMYzJpOaAzi3ZbJUn_fvYsh1CavfmKG-uxITq3XhajubneQZhW6xY7kYUjgBAm5ZuR0nHkwYw9__39uBKYs_eTa-Pfb7vhCwuybqQeGs9JgN0vFur1)

You should see "Push to master branch" in the list of triggers. Congratulations, you've created a build trigger! 

Your repository should now be setup for build triggers.


## Triggering a build

*Duration is 10 min*


### __Running a trigger manually__

The normal way to trigger a build is to meet the conditions set in the build trigger. In the case we've created, that would require pushing changes to the master branch of the repository. As a way to test out the trigger and to quickly get familiar with the Cloud Build UI, you're going to force the trigger to run manually by clicking on the "Run trigger" button for it on the Build triggers page. 

![fIkHlpA9IR8CT4EBcE-rP4gff3NE3lCZMAoosa_G4hE42GxJP9gj96d-37U7rETOAadD9yoHL51IziLuCjbAe1PzoJEYMcObRdfnXQ6wkZXSX0y2EYETvxgOZsKKMbJ168NpFl2b](https://lh4.googleusercontent.com/fIkHlpA9IR8CT4EBcE-rP4gff3NE3lCZMAoosa_G4hE42GxJP9gj96d-37U7rETOAadD9yoHL51IziLuCjbAe1PzoJEYMcObRdfnXQ6wkZXSX0y2EYETvxgOZsKKMbJ168NpFl2b)

When you click on the "Run Trigger" button on your "Push to master branch" it will ask you which branch you want to run the trigger on, so choose "master". You should see a toast that says "Build started". 

Switch to the "Build history" page to see the build status.

![4dqnBKu7hH1AKFN8g438uDYWvOxG0kY-TH3KvIPU1lHtfEQ5DBt-D1PMcpAnJO1_U1z1WDoi1qsp6l3FySaGfVg5UXUm_KfZKBjXM5BMYIvohjKhYn9UibMeazyf7mwvCPfRX9H9](https://lh3.googleusercontent.com/4dqnBKu7hH1AKFN8g438uDYWvOxG0kY-TH3KvIPU1lHtfEQ5DBt-D1PMcpAnJO1_U1z1WDoi1qsp6l3FySaGfVg5UXUm_KfZKBjXM5BMYIvohjKhYn9UibMeazyf7mwvCPfRX9H9)

You should see the build listed, along with the status. Click on your build to navigate to the "Build details" page.

![OekI5H10iiS2JUt7sD3HULAu0toZiUspIynEtAM9i4Zkd0qJ-AbLKlcfEVs4fAOybDEVvpMPmfdO-rYKLZCnzIGu1oTKPRs6LIzxZVelIL3jnf3SEQl2lAqOar1y0EGTHQ0KutaO](https://lh3.googleusercontent.com/OekI5H10iiS2JUt7sD3HULAu0toZiUspIynEtAM9i4Zkd0qJ-AbLKlcfEVs4fAOybDEVvpMPmfdO-rYKLZCnzIGu1oTKPRs6LIzxZVelIL3jnf3SEQl2lAqOar1y0EGTHQ0KutaO)

This is an overview of all the things that comprise your build. The top part of the page shows a summary of the build process, the middle is a list of the steps that were performed, and the bottom of the page has the logs from those steps. These logs should look somewhat similar to the results you saw when you manually deployed your website. If you look through the logs you should see a line that has a link to the `target url` (highlighted above), which like before shows the URL to your site. If you go there, you should still see your test page. Given that the code hasn't changed, you shouldn't see any difference.

### __Triggering a build normally__

Time to try out the trigger via the normal process. You'll make a change to your local files, commit and push them to the remote repository, where the trigger should see the change and automatically publish the site. 

Using a text editor, open the `index.html` file in your projects' `www` directory. This is the HTML for your website, so make a change to it that you'll be able to see when the site is updated, say editing the text in the `<h1>` or `<p>`. Once you're happy with the edits to the file, save it. You now have local changes, so commit them as you normally would.

    git add .

    git commit -m 'text edits in index.html'

Then push them to the remote repository.

    git push origin master

Your changes should now merge into the master branch on the remote repository. This should trigger a build, so go to Build history to see the build status.

![Ufxo5zK5BN4oYTFQKMJxwXeRdHtcgallDhcHSg2_ftIPz-fvEBYm3e3AbjHSclGzp8FSn2BJaQQsa1Pq7rUJN1Q6YalhzKn4yESR4XymS62_XzOIMeQbNwXGqiufBCtEaJKmb1kf](https://lh4.googleusercontent.com/Ufxo5zK5BN4oYTFQKMJxwXeRdHtcgallDhcHSg2_ftIPz-fvEBYm3e3AbjHSclGzp8FSn2BJaQQsa1Pq7rUJN1Q6YalhzKn4yESR4XymS62_XzOIMeQbNwXGqiufBCtEaJKmb1kf)

If your build was successful, go see your changes live in your test page. If you've left a tab open in your browser for your test page, you'll need to refresh it to see the changes.

![xlUZteqYfoacv5Ey7Wwa9yvWoaJL4N4rL-U1dWxsCJgdaRgo1-He3lUlUgn516pJMK6IVoagxWXSqxJg1XJO2KWlADbwFy4Jc6X56vOknXZeQKrq7rJdk5l_vwk6JyjwcYk9i3dc](https://lh5.googleusercontent.com/xlUZteqYfoacv5Ey7Wwa9yvWoaJL4N4rL-U1dWxsCJgdaRgo1-He3lUlUgn516pJMK6IVoagxWXSqxJg1XJO2KWlADbwFy4Jc6X56vOknXZeQKrq7rJdk5l_vwk6JyjwcYk9i3dc)

You've successfully automated the build process for your website. Every time you check in changes to the master branch your site updates without having to manually deploy it. 


## Setting up Cloud Code Review

*Duration is 5 min*


Cloud Code Review is based on the open source Gerrit project. It is a lightweight framework built on top of Git to enable peer-reviewing of commits before they are merged into the codebase. In previous steps you were able to push your changes into the remote repository (merging the codebase) without review. You're going to change this process to require changes be reviewed before they can be merged into the master branch.

### __Enabling code review__

Go to  [Cloud Source Review](https://source.cloud.google.com/), __select your repository__, and click on the gear icon to open up the settings for the repository.

![smN3DeB-JwyZpwcaXTShTU97xJfMiCPr7LVWz07JcbboNFpoovNJ12e3LcMwu93FQfEWJedxHWHp2sSTczo1gxQgMrD6oxdcaFoDMLZpwqFMWrMJ8Xn8ek48Z-VtCXK5LbpVDgj1](https://lh3.googleusercontent.com/smN3DeB-JwyZpwcaXTShTU97xJfMiCPr7LVWz07JcbboNFpoovNJ12e3LcMwu93FQfEWJedxHWHp2sSTczo1gxQgMrD6oxdcaFoDMLZpwqFMWrMJ8Xn8ek48Z-VtCXK5LbpVDgj1)

Choose "Code review settings" from the menu, and select "Require code review for master only". Click "Save".

![6DbLJbJ806InJldHuhvBWQr3cBvnL23eY9GpDgH5FoJ6UkCO7u4WNq1cvX1NqKlyjysdiLAznWVfT_veNlXSKgpgPdCAHFvjs11FlkkDk2Lu5o8Tr7nZ7HvcJtTTdWqTuL6oQZkN](https://lh3.googleusercontent.com/6DbLJbJ806InJldHuhvBWQr3cBvnL23eY9GpDgH5FoJ6UkCO7u4WNq1cvX1NqKlyjysdiLAznWVfT_veNlXSKgpgPdCAHFvjs11FlkkDk2Lu5o8Tr7nZ7HvcJtTTdWqTuL6oQZkN)

Your repository is now configured to use Cloud Code Review for any changes to the master branch of your repository. Other branches are unaffected and work normally in Git.

### __Installing the commit hook__

Another requirement for Cloud Code Review is that commits need to have a "Change ID". This requires you to add a "hook" to the git command line tool so that this information is automatically added to each commit. 

In terminal enter the following command:

    f=`git rev-parse --git-dir`/hooks/commit-msg

You shouldn't see any output from this command as all you've done is define a variable for where the hook should go. Now enter the following:

    curl -Lo $f https://gerrit-review.googlesource.com/tools/hooks/commit-msg

This time you should see output giving status on a download. You've just copied a bash file into your repository's Git configuration that will append a Change ID to each commit. This file needs to be made executable, so enter the following command:

    chmod +x $f

Again, you shouldn't get any output. You've now added and configured the commit hook to your local repository. 

You should now be set up for Cloud Code Review.


## Creating a Code Review

*Duration is 5 min*


You should be all set up to use Cloud Code Review, so let's try it out. In order to have a code review you'll need to commit new changes. 

Open the file `index.html` file in your text editor, make changes to it like you did for the build trigger step, and save the file.

Now commit the changes into your local repository, the same as you normally would, via the following git commands:

    git add .

    git commit -m 'updates to index.html'

Your local repository now has a committed change, so normally you would `push` that change to master. Let's try that:

    git push origin master

You should have gotten an error stating that master requires code review. This is good, as it means that you can't commit code to the master of your repository without review.

So how do you push your changes for code review? That's done by pushing the changes to a special branch, `HEAD:refs/for/master` which is used by Cloud Code Review to hold changes awaiting review. You can push your changes there by the following git command:

    git push origin HEAD:refs/for/master

This time you should see a successful push message, so go back to your Cloud Source Repository page. If you look at the index.html file there, you'll notice that your edits are not showing, but that's because they're still awaiting review.

![PDM5HG1PcudJeQYHAQpYSMMABIsNzG3KjpvLgKvKVe6xv7MikTS5rTACviHLBzAiWpLPLHxGJwu-QpBzuVatxOTe9-LWkzzuowT4SFJ8BYtGOVKBLvJXFJzdPdJTtEcNzH4DHoMs](https://lh4.googleusercontent.com/PDM5HG1PcudJeQYHAQpYSMMABIsNzG3KjpvLgKvKVe6xv7MikTS5rTACviHLBzAiWpLPLHxGJwu-QpBzuVatxOTe9-LWkzzuowT4SFJ8BYtGOVKBLvJXFJzdPdJTtEcNzH4DHoMs)

Click on the Cloud Code Review menu item to go to your Cloud Code Review dashboard.

![wKp-tvu1zGAF0xy5RH4obek-2lbJyuTp7vB55-XawKKExNkuGUWpKoTXIIR6594ieLUbhuuX1hBGYGSgOecxijF5CE1Nf_i-GmxX77fGkVvhOkR8Y_UEStE6BF6h41Fz22j6TFGa](https://lh6.googleusercontent.com/wKp-tvu1zGAF0xy5RH4obek-2lbJyuTp7vB55-XawKKExNkuGUWpKoTXIIR6594ieLUbhuuX1hBGYGSgOecxijF5CE1Nf_i-GmxX77fGkVvhOkR8Y_UEStE6BF6h41Fz22j6TFGa)

You should see your commit listed under the "Outgoing reviews". You've successfully created your first code review!


## Reviewing code

*Duration is 10 min*


In the previous step you created a code review, so let's see how it works.

### __Quick tour of the Code Review interface__

Click on your review in the dashboard and you'll be taken to the review interface. It's packed with features, so it's worth taking a quick tour. We'll briefly cover the following five areas of the UI.

![5TATVXUfbyUcnVqMmC1wmeMLdUvQ6fm964kF1jhGE7lG1-B98cVzIC7rt2BINgX3u7M_acoAWk2V08el6ymgx1tljcxSjlx4Vjo-0XnSkX5vzqPXqlHgfOJVpoEJgz4KAmiB-1Pd](https://lh4.googleusercontent.com/5TATVXUfbyUcnVqMmC1wmeMLdUvQ6fm964kF1jhGE7lG1-B98cVzIC7rt2BINgX3u7M_acoAWk2V08el6ymgx1tljcxSjlx4Vjo-0XnSkX5vzqPXqlHgfOJVpoEJgz4KAmiB-1Pd)

#### __1. The list of reviewers__

![Rm5R-OKtwLZlwcjm4CC8UUCwMg5IoMSzcNAKCw-AdelqZRI2t9e11WCcrnsFj5weDQoKwHLa2I-BLk9zvpbk1ZYXeCGGoUcC5IE9S8bw42bVt1-1nkjt6LtArMRgA2iGMg3tLYVU](https://lh4.googleusercontent.com/Rm5R-OKtwLZlwcjm4CC8UUCwMg5IoMSzcNAKCw-AdelqZRI2t9e11WCcrnsFj5weDQoKwHLa2I-BLk9zvpbk1ZYXeCGGoUcC5IE9S8bw42bVt1-1nkjt6LtArMRgA2iGMg3tLYVU)

This is the list of reviewers. Normally when collaborating with a team on code, you would add specific people you will want to review your edits. Because you're working solo on this tutorial, leave this as is for now.

#### __2. Review requirements__

![Z450EY3k216PrKJkQEmM6OB19rlcA9g1UY4sbX5yrIwfpp72y0eOCcDnGdw1I4wBor1ofrdz6RdrkYetvTTfN2RmgS6rRNbHOckQAME8HPO8Jb1bA6rLXUG6eCKlSXjUTL9ajyHr](https://lh5.googleusercontent.com/Z450EY3k216PrKJkQEmM6OB19rlcA9g1UY4sbX5yrIwfpp72y0eOCcDnGdw1I4wBor1ofrdz6RdrkYetvTTfN2RmgS6rRNbHOckQAME8HPO8Jb1bA6rLXUG6eCKlSXjUTL9ajyHr)

This section lets you know the requirements that need to be met before the change can be submitted. The orange hourglass icon lets you know you haven't met the requirement yet. In this case the only requirement is for the review to be upvoted, which you'll do shortly.

#### __3. File list and diffs__

![1nCMh9iK0PkPJY5GYBK1OWmK2bJp0Nh1BwUy9kv55kiflaQS4tPv0ffEypRbrcb3Tzyrkf5j3rDLOX9wczjmc31gyHjMeTL_179rATYNN2cy7pu2hhNVy6QTAMw7RUO6v3NBD3Dk](https://lh4.googleusercontent.com/1nCMh9iK0PkPJY5GYBK1OWmK2bJp0Nh1BwUy9kv55kiflaQS4tPv0ffEypRbrcb3Tzyrkf5j3rDLOX9wczjmc31gyHjMeTL_179rATYNN2cy7pu2hhNVy6QTAMw7RUO6v3NBD3Dk)

This area contains the files that have been modified as part of the change. You can click on each file in the list to view the diffs for that file. When the diffs are being viewed, you can select any section of text to create a comment. 

#### __4. The reply button__

![YUAFq5hp8qvChGztND0Viw998f1wb9fO-XXT9lfOYo6KpNzkdmz7G7s6MWv7ZYM0zmFuy9MWga6OA2aLxmYfKbS_clwOV3SCxIVufZPgidlMiLlAFG7-3BRIRi080PArpAKC2Buv](https://lh6.googleusercontent.com/YUAFq5hp8qvChGztND0Viw998f1wb9fO-XXT9lfOYo6KpNzkdmz7G7s6MWv7ZYM0zmFuy9MWga6OA2aLxmYfKbS_clwOV3SCxIVufZPgidlMiLlAFG7-3BRIRi080PArpAKC2Buv)

In Cloud Code Review, you need to use the "Reply" button to send your comments to the author, otherwise they are only visible to you as drafts.  

#### __5. The action bar__

![nXdF87M82kc-l8H4fmni0kkVTCROMInoxm48Sb6jwHj_WpVcnwJF4iBrcxgIVXlFZKMmCjdCryIFisCLBzMGrNvdQII3iKXIObolA4kMwrqT1zwtaBPbQsX1on0ATD5cUBVdb_V7](https://lh4.googleusercontent.com/nXdF87M82kc-l8H4fmni0kkVTCROMInoxm48Sb6jwHj_WpVcnwJF4iBrcxgIVXlFZKMmCjdCryIFisCLBzMGrNvdQII3iKXIObolA4kMwrqT1zwtaBPbQsX1on0ATD5cUBVdb_V7)

This area contains the buttons you use to take major actions on the code review. As a reviewer, you'll see a "Code Review +2" button here that you can use to approve the changes for submission. The "Rebase" button is used to sync with other changes that may have occurred, which you won't need to deal with here. The "Abandon" button is used to reject these changes and remove them from review. 

Once the review has met all of the submission requirements (see #2 above), the "Code Review" button is replaced with a "Submit" button which will merge the changes into the codebase.

### __Approving and Submitting the changes__

Because you don't have a team to review your code, as author you can approve your changes yourself via a two step process. First, click on "Code Review +2" to upvote the changes. By upvoting these changes they have met the requirements for the review, so you'll now see the "Submit" button. 

![nauJT9eMMM8BaKKQ8Th2LupWQzLGdGQo8EQA5TEdmLYNC2J6Hbo-gOlwOnugDdZjIc-b3KW13wpr3nVMMHj721X1GCsZAZf2bY_r8qu0tOhp-WcAEL8ONiQ-Z-HBBhcYfA8ao-nG](https://lh5.googleusercontent.com/nauJT9eMMM8BaKKQ8Th2LupWQzLGdGQo8EQA5TEdmLYNC2J6Hbo-gOlwOnugDdZjIc-b3KW13wpr3nVMMHj721X1GCsZAZf2bY_r8qu0tOhp-WcAEL8ONiQ-Z-HBBhcYfA8ao-nG)

Clicking on the "Submit" button will present a confirmation dialog as a last check before merging the changes. Click "Continue" in the dialog and your changes will merge into master. Click on "Your Dashboard" and you'll see that your review has moved from "Outgoing reviews"  to "Recently closed" indicating that the review is complete. You've successfully created, reviewed and submitted your changes!

### __Check the build__

By submitting the changes, you have merged them into the master branch, which in turn should have triggered a build. You can check the build status on the Build history view in Cloud Build, or go to your test page to see the results.

Congratulations! You've completed the tutorial.



