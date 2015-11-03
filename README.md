# Nodevember Azure Code Challenge
 
![Nodevember logo]('CodeChallenge.png')
 
## Deploy your Node web apps on Azure

Did you know Node apps can be hosted on Microsoft Azure? Yes, that means your Node apps (and Express, Socket.io, Sails.js and more!). Microsoft Azure is about much more than just Windows and .NET.

Microsoft Azure offers a wide array of creation, deployment and management capabilities through the Azure Management Portal, the cross-platform command-line interface, or the PowerShell cmdlets.

## The Challenge
* Clone any Node GitHub repo or use one of your own existing Node apps
* Run the app locally to confirm it's working
* Modify with your own information
* Deploy the web app to Azure
* That's it! You've completed the challenge. Stop by the Microsoft booth to get your custom, limited-run trucker hat!


>### TL;DR
You could just skip all of these steps by forking the GitHub repo and deploying the app using the easy "Deploy to Azure" button. We get it. You're busy eating [hot chicken](https://www.thrillist.com/eat/nashville/nashville-s-best-hot-chicken-restaurants), making new Node friends, and catching up with old ones. We won't hold it against you and you still get the cool Trucker Hat. But that's not much of a challenge, now is it?

## Prerequisites

*To complete this challenge you'll need* 
* [Microsoft Azure account](http://azure.microsoft.com)
 * Sign up for a free trial, or get a free $100 Azure pass from the Microsoft booth. 
* A code editor
 * We use [Visual Studio Code](https://code.visualstudio.com/), it's free, cross-platform and great for Node debugging. You can also use Sublime Text, Vim or any editor of choice
* [Node.js](https://nodejs.org/en/) runtime and tools installed
* [GitHub](http://github.com) account created and/or Git
* Windows, Mac or Linux

## Steps
These steps describe how to get started running Node on Azure Web Apps.

This is Nodevember, so we'll be using the Node.js of course with the Express web framework. You will create a web app from Azure, set up deployment via local Git or GitHub. Then you will run the application locally, make changes, commit and push them to Azure. We'll show how to do this from Windows or Mac/Linux. 

### Step 1: Create a Web App in Azure

The first step in creating your app is to create a web app via the Azure Portal. Azure Web Apps support Python, .NET, Java, PHP, and Node.js. 
1. Log into the Azure Portal
 and click the NEW button in the top left corner. Click Web + Mobile > Azure Marketplace > Web Apps. 
 
2. Click Web + Mobile > Azure Marketplace > Web Apps 
3. Configure the new Node app, by creating a new App Service plan and a new resource group for it. Your app name will be your sub-domain and will need to be unique. 
4. Then, click Create to complete your app
5. Click Web + Mobile > Azure Marketplace > Web Apps to show your website. Sweet. Now we have a site created, let's put something in it.

### Step 2: Clone the Nodevember Challenge repo and run locally

Our goal here is to create a very simple website. You have a few options, but the simplest one is to simply fork the GitHub and clone locally:

1. Fork this repo: https://github.com/dxhackers/YourNodeSite
2. In the git console call: git clone https://github.com/<your_user_name>/YourNodeSite.git NodevemberChallenge
3. cd NodevemberChallenge 

#### Let's pause and take a look at the app structure
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
It's a very basic Node app. The following files are needed to deploy your Node application to Azure.

* **packages.json** - External packages needed by this application. The Azure environment will use this file to 'npm install' the packages listed in this file.

* **.deployment and deploy.cmd** - These aren't actually needed here because we're not doing anything that requires a custom deployment script. We've included them so you can understand what the build environment ([Kudu](https://github.com/projectkudu/kudu)) is doing once it determines this is a Node app.

### Step 3: Create virtual environment

Now that you've got the code on your local machine, let's run it localy. Choose instructions below to set up via the command line (Windows, Mac, or Linux) or in Visual Studio (Windows).

1. Open your Node.js console
2. Navigate to your folder
3. type 'npm install' to install the dependencies for the project 
4. You should now be able to run project by typing 'node app.js'
  * If you're using [Visual Studio Code](http://code.visualstudio.com), simply hit F5 to start the app.

### Step 4: Modify with your own information

1. Open /app.js and modify the YOUR_INFO with your information.
 
2. After you've tested your changes, commit them to the Git repository:
 * git add .
 * git commit -m "Add my contact info"

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
