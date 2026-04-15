# Setup and Deployment
For this competion, we are currently using [CTFd](https://ctfd.io/) to host the challenges locally.
We do not leverage all of the features of CTFd as there are technical limitations to how the competition is run and hosted at the state conference.
This guide will show how to setup and configure CTFd for our needs.
Once done, this document will work for both local testing and production deployment for the competition

## Runing CTFd
There are multiple way to get up and running with CTFd.
Their [GitHub repository](https://github.com/CTFd/CTFd) list the details of the different ways.
For local testing, we'll use Docker or Podman to run an instance.

**Docker Command:**
```shell
docker run -p 8000:8000 -it ctfd/ctfd
```

**Podman Command:**
```shell
podman run -p 8000:8000 -it ctfd/ctfd
```

Feel free to adjust the run command as needed for your requirements.

### Kubernetes
For production deployment, we'll make use of a Kubernetes cluster to run CTFd.
Details of this are still being worked out and will be updated once complete.

## Setup
Once you have an instance up and running, CTFd has it's own setup screens.
These allow for basic platform and event configuration.
There is not a good way to automate this section, so you will need to manually set it up.
Below outlines what values need to be set in the UI for the competition.

### General
Enter the following details:

- Event Name
  > PA TSA High School Cybersecurity
- Event Description
  > Applying leadership and 21st-century skills, participants respond to a cybersecurity challenge by identifying a breach in computer security via "Capture the Flag" games.
    Areas of challenge might include exploit development, digital puzzles, cryptography, reverse engineering, binary analysis, mobile security, etc.
    Participants must accurately address a series of on-site problems within a specified, limited amount of time.

### Mode
Select "Team Mode"

### Settings
- Challenge Visibility
  > Private
- Account Visibility
  > Admins Only
- Score Visibility
  > Admins Only
- Registration Visibility
  > Private
- Verify Emails
  > Disabled
- Team Size
  > 6

### Administration 
- Admin Username
  > pa-tsa-admin
- Admin Email
  > pa-tsa-admin@patsa.local
- Admin Password - Enter a value you will remember
- Uncheck "Subscribe email address to the CTFd LLC Newsletter for news and updates"

### Style
Leave all defaults and hit next.

### Date & Time
Set a start and time that makes sense for either testing or the event itself.

### Integrations
- Social Shares
  > Disabled
- MajorLeagueCyber Integration - **Do not setup**

## Configuration
After the setup is complete, you'll be logged in as the admin account you created during the setup.
In order to automate the rest of the configuration, we need to generate an access token for the admin account.

- Navigate to the settings page by hitting the "Settings" link at the top of the screen.<br>
  If you using Docker and `localhost`, the URL is http://localhost:8000/settings.
- Click "Access Tokens"
- Select an expriation date that makes sense for you
- Enter "CTFd CLI" for the description
- Hit "Generate"

A dialog will popup that contains the generated access key.
It will be the format of:
```
ctfd_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

Store this value in a safe place as we'll need it for the next steps.

##

-> Note: Add step to award 20 points to all teams. This is to get around issues with CTFd and negative scores