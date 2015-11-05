# Nodevember Azure Code Challenge
 
![Nodevember logo]('CodeChallenge.png')
 
## Deploy your Node web apps on Azure

Did you know Node apps can be hosted on Microsoft Azure? Yes, that means your Node apps (and Express, Socket.io, Sails.js and more!). Microsoft Azure is about much more than just Windows and .NET.

Microsoft Azure offers a wide array of creation, deployment and management capabilities through the Azure Management Portal, the cross-platform command-line interface, or the PowerShell cmdlets.

## The Challenge
* Clone any Node GitHub repo (including this one!), or use one of your own existing Node apps
* Run the app locally to confirm it's working
* Modify with your own changes
* Deploy the web app to Azure
* That's it! You've completed the challenge. Stop by the Microsoft booth to get your custom, limited-run trucker hat!


>### TL;DR
You could just skip all of these steps by forking the GitHub repo and deploying the app using the easy "Deploy to Azure" button. We get it. You're busy eating [hot chicken](https://www.thrillist.com/eat/nashville/nashville-s-best-hot-chicken-restaurants), making new Node friends, and catching up with old ones. We won't hold it against you and you still get the cool Trucker Hat. But that's not much of a challenge, now, is it?

## Prerequisites

*To complete this challenge, you'll need:* 
* [Microsoft Azure account](http://azure.microsoft.com)
 * Sign up with an email that ends in Hotmail, Live, or Outlook for a free trial, or get a free $100 Azure pass from the Microsoft booth. 
* A code editor
 * We use "[Visual Studio Code](https://code.visualstudio.com/)": it's free, cross-platform, a lightweight 5-minute download, and great for Node debugging. You can also use Sublime Text, Vim, Notepad++ or any editor of choice.
* [Node.js](https://nodejs.org/en/) runtime and tools installed
* [GitHub.com](http://github.com) account created
* [Git](http://git-scm.com/) version control and tools (Terminal and Git Bash) installed 
* Windows, Mac, or Linux OS

## Steps
These steps describe how to get started running Node on Azure Web Apps.

This is Nodevember, so we'll be using Node.js (of course) with the Express web framework. You will create a web app from Azure, set up deployment via local Git or GitHub, then you will run the application locally, make changes, commit, and push them to Azure. We'll show how to do this from Windows, Mac, or Linux. 

### Step 1: Create a Web App in Azure

The first step in creating your app is to create a web app via the [Azure.com Portal](http://azure.microsoft.com). Azure Web Apps support Python, .NET, Java, PHP, and Node.js. 

1. Log into the Azure Portal using your Microsoft Account (this is anything that ends in Hotmail, Live, Outlook, or signs you in to Skype, Xbox LIVE, OneDrive, or Windows Phone) and click the NEW button in the bottom left corner. 
 * If you see the “No subscriptions found” page, you can either:
   - Sign up for a free trial using the Sign up for Windows Azure link
   - Go get a free $100 Azure pass from the Microsoft booth.

2. Click Web App > Custom Create. Configure the new Node app by creating a new App Service Plan, but no database is necessary. Your app name will be your sub-domain and will need to be unique. 

3. We recommend setting Region to Central US. Do not publish from source control just yet.

4. Click the Create checkmark to complete your app.

5. Once your Web App has finished loading, click its URL to show your website. (Alternatively, click its name > Dashboard > URL). Your web app has been successfully created! Sweet. Now that we have a site, let's put something in it.

### Step 2: Clone the Nodevember Challenge repo and run locally

Our goal here is to create a very simple website. You have a few options, but the simplest one is to simply fork the GitHub and clone locally:

1. Fork this repo: https://github.com/SarahSexton/NodevemberMS (Go to that site and click the fork button at the top right. Once the fork animation is complete, you've got a copy on your account. Copy your fork's HTTP URL on the right sidebar.)
2. In [Git Bash](opensourcerer.diy.org/challenge/3), navigate to a directory where you want to save the GitHub folders (using "cd .." to go up, "dir" to display the directory, "mkdir" to make a new directory folder, and "cd <folder_name>" to change directories into a folder).
3. Clone the repository onto your computer. It will create a new folder for the repository, so no need to create one. But make sure you aren't cloning it inside of another Git repository folder! You can leave the folder you're in (and be in the folder that it was inside of) by 'changing directory' with two dots: 'cd ..'
4. Type: 'git clone https://github.com/<YOUR_USERNAME>/NodevemberMS.git' 
5. Go into the folder for the fork it created (in this case, named 'NodevemberMS') with 'cd NodevemberMS'
6. Now you've got a copy of the repository on your computer and it is automatically connected to the remote repository (your forked copy) on your GitHub account.

#### Let's pause and take a look at the app structure:
- public
    - default.html
    - default.js
    - default.css
- app.js
- package.json
- readme.md
- .deployment
- deploy.cmd
- .gitignore

#### Files needed for Azure
It's a very basic Node app. The following files are needed to deploy your Node app to Azure:

* **package.json** - External packages needed by this application. The Azure environment will use this file to **'npm install'** the packages listed in this file.

* **.deployment and deploy.cmd** - These aren't actually needed here, because we're not doing anything that requires a custom deployment script, but we've included them so you can understand what the build environment ([Kudu](https://github.com/projectkudu/kudu)) is doing once it determines this is a Node app.

### Step 3: Create virtual environment

Now that you've got the code on your local machine, let's run it localy. Choose instructions below to set up via the command line (Windows, Mac, or Linux) or in Visual Studio (Windows).

1. Open your Node.js console
2. Navigate to your folder (using "cd .." to go up, "dir" to display the directory, and "cd <folder_name>" to change directories into a folder)
3. type **'npm install'** to install the dependencies for the project 
4. You should now be able to run project by typing **'node app.js'**
  * If you're using [Visual Studio Code](http://code.visualstudio.com), simply hit F5 to start the app.

### Step 4: Modify with your own changes

1. Open 'app.js' and modify the YOUR_INFO with your information.
 
2. After you've tested your changes, commit them to the Git repository:
 * **git add .**
 * **git commit -m "Add my contact info"**

### Step 5: Deploy the Web App to Azure

Going back to the Azure Portal, we can now push our code to Azure. There are many ways to deploy code to Azure, but for now we'll focus on using Git.

1. Navigate to your web app in the portal by clicking the tile on your portal's home screen or by finding it under Browse All > Web App. Once on your web app's page, scroll down to the bottom to setup Continous Deployment. Choose either GitHub or Local Git Repository.
 
 * If you chose GitHub, simply authenticate with your Azure credentials and choose your Nodevember project. Notice that you can select branch configuration as well if you want to use this for dev or staging. Azure will listen for changes on this repo and kick off a deployment anytime a commit is pushed.
 
 * If you chose Local Git Repository, an empty Git repo will be provisioned for your web app. You'll need to get the URL of this repo to add it as a remote for your local copy. Click on Settings > Properties and copy your Git URL.
    1. After you copy the URL, open up your command prompt and navigate to your local project. Add Azure as a remote and do a push.
    2. git remote add azure YOUR_GIT_URL
    3. git push azure master

3. No matter which method you chose, Azure will have grabbed the latest version of your web app and started the deployment. You can always see the status of deployments and view the log. Go ahead and take a look. You'll see that Azure figured out that this is a Node project, detected which Node runtime to use, installed a virtual enviroment, npm installed Express from packages.json, collected static files, and more.
 
## Congrats! You've just deployed your app to Azure!

Come by the Microsoft booth for your awesome trucker hat.

You can find additional resources and infomation about Azure deployments here. 

If you would like some help creating your site or are looking for ideas come by the Microsoft Booth or shoot us a tweet: 

Stacey Mulcahy [@bitchwhocodes](https://twitter.com/bitchwhocodes)
 | Sarah Sexton [@Saelia](https://twitter.com/Saelia)
| Ryan Joy [@atxryan](https://twitter.com/atxryan)
