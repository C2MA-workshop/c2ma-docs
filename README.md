# c2ma-Setup Steps
Set up instructions for the workshop.  All that is required ahead of time is a valid institution email which you will use to create an IBM Cloud account. If you have not already created an IBM Cloud account as part of the PAIRS registration process, the details are below. Please use lowercase letters when entering your email address.

## Create an IBM Cloud account

Click on [https://ibm.biz/COP26-workshop-2021](https://ibm.biz/COP26-workshop-2021)

Fill in Account information, email and other information as required.  You will receive a verification code to the email you specified.  Note that this code is only valid for 30 minutes.

Enter the Verification code and then an Personal Information (like password and country). 

Read the IBMid Account Privacy information and if you agree with it, scroll down and click Proceed.

You now have an IBM Cloud account which is linked to your email.

You will see a Welcome message, if you wish to have a Tour then click "Show me" otherwise click "Maybe later".  We recommend to click "Maybe later" for now.

You are presented with the initial screen of services available for you.  Note : you have what is called a "Lite" account which means that you can have access to the Free/Lite resources of each of the Services and can investigate their functionality without charge.

If you have an older IBM ID already then there might be some further setup steps for you to be able to create the Watson Studio Service later on in this setup guide.  Contact Stefan on kwiatks@uk.ibm.com if you have an old account (and cc anne.jones@ibm.com as well).

![login-image](./images/logged-in-user.png)

## PAIRS API key and github

You should have been allocated a PAIRS API key against your own email.  If you do not have one then contact anne.jones@ibm.com.

Create a file called "pairpass.txt" on your own machine and copy the API key to it

Obtain the files from this github and copy them onto your own machine, there are two ways of carrying this out :

(a) Create a sub-directory of your choice on your own machine and clone the github with the following command :

git clone https://github.com/C2MA-workshop/c2ma-docs.git

(b) Create a sub-directory of your choice on your own machine and then click on Code -> Download ZIP and save the zip file.  Unzip the zip file to be able to access all the files from this github.

![login-image](./images/github-copy-local-machine.png)

We will use some of the files later in this setup guide




## Setup Watson Studio Service and create a Project

Login the IBM Cloud

Click on Create Resources

![login-image](./images/create-resources.png)

Type "Watson Studio" in the search bar and click the "Watson Studio" item

![login-image](./images/pick-watson-studio.png)

For Select a location, pick "London (eu-gb)" - this might be the default for you anyway.  The Lite Plan is automatically selected.


Click "Create"

![login-image](./images/create-watson-studio.png)

Wait a few seconds and the Watson Studio instance will be shown.

Click "Get Started"

![login-image](./images/get-started-watson-studio.png)

Enter some further information.  NOTE : you need to pick your international code froom the drop down and then enter your telephone number in the field next to the code otherwise the Continue button will not be enabled.

Click "Continue"

![login-image](./images/get-started-more-info-ws.png)

A range of Services to provision will be shown, for now click "Continue"

![login-image](./images/services-to-provision-ws.png)

Watson Studio is configured.

Click "Go to IBM Watson Studio"

![login-image](./images/go-to-ws.png)

If you receive any survey prompt - ignore them and continue.  Also, you will be prompted for a "Welcome to Cloud Pak for Data" tour - click the cross to skip this tour.

![login-image](./images/cp4d-ignore-ws.png)

You will now see the main Watson Studio dashboard

![login-image](./images/main-ws-dashboard.png)

Click on "New Project"

![login-image](./images/new-project-ws.png)

Click on "Create an empty project"

![login-image](./images/create-project-empty-ws.png)

Before a project can be create, it needs somewhere to be saved to.  Watson Studio using Cloud Object Storage (COS) to save it's artifacts into.

NOTE : you only need to create the COS storage once and then after that all your projects will be stored in it.

Click "Add"

NOTE : A new Tab will be opened in your browser

![](./images/create-project-empty-add-cos-ws.png)

Leave the Lite Plan as shown and click "Create"

![](./images/create-cos-ws.png)

NOTE : No prompt appears that the storage has been successfully created.  Return back to the Tab where you clicked "Add" and refresh the whole page in your browser.  The below screen shows **Cloud Object Storage-an **has been created

![login-image](./images/cos-done-ws.png)

Enter a project name "test-<add something unique>" followed by your initials or something unique and then click "Create"

You might be asked if you wish for a Tour of Watson Studio - cancel any prompt unless you do wish to go on the Tour

![login-image](./images/project-test-ws.png)

You will see your project main screen

![login-image](./images/project-main-screen-ws.png)

On the main screen click "Add to project" and then click on "Data"
![login-image](./images/project-add-file-ws.png)

You will be presented with an option to Upload a file

![login-image](./images/project-add-pairspass.png)

Drag or click Browse to upload your pairspass.txt file

![login-image](./images/project-add-pairspass-file.png)

Check the file has been uploaded succesffuly

![login-image](./images/project-add-pairspass-file-check.png)

Now you need to carry out some project type settings.  Click on the Settings Tab

![settings](./images/project-settings.png)

Scroll down to the Access tokens section and click on "New token +"

![settings](./images/project-settings-new-token.png)

Enter a Name and pick Editor for "Access role for project" pick Editor and then click Create

![settings](./images/project-settings-new-token-values.png)

View the token 

![settings](./images/project-settings-new-token-view.png)

Cut/paste the value to a text file on your machine (we will use this within a Notebook later on)

![settings](./images/project-settings-new-token-view-it.png)

Click on the Projects link

![settings](./images/project-id1.png)

Then click on your project (for example test-sjk) and look at the URL of the browser and copy and save away the ProjectID.  Again, this will be used in a Notebook

![settings](./images/project-id2.png)

## Import test Notebook to Watson Studio

Go to your project and click "Add to project +" 

![settings](./images/project-import-notebook1.png)

Select Notebook

![settings](./images/project-import-notebook2.png)

Click "From file" tab and either drag/drop the test-notebook.jpynb from the location on your machine or click "Drag and drop files here or upload" and go to it's location on your machine.  NOTE : the file is under the **test** sub-folder of the cloned repository

In the Select runtime drop down leave the default of "Default Python 3.7 XS (vCPU 8 GB RAM)" but note that this can be changed if you are using up a lot of capacity unit hours allocated to you

Click Create

![settings](./images/project-import-notebook3.png)

The Environment will be initialised - please wait a few moments, you will see a cicular progress icon.

When the Notebook is loaded click on the "Get project details" section and change both the project_id and project_access_token values to the ones you created and saved away earlier.  If you don't change them then (a) any import/export will not work and (b) if you do any exporting of files they will potentially get created in the test users project used to create these steps !!

![settings](./images/project-import-notebook4.png)

Save the project by clicking File -> Save 

![settings](./images/project-import-notebook5.png)

To Run the whole Notebook click on the double arrow icon and click "Restart and Run All Cells" in the prompt that comes up

![settings](./images/project-import-notebook-run-all.png)

A * appears on each of the running cells and if successful then you should see the following at the output on the last cell.  Ignore the GeoPandas message.


![settings](./images/project-import-notebook-run-check.png)

If you see the above outout this proves that you have successfully configured and executed a Notebook against IBM PAIRS.

Please now continue with other Notebooks of this workshop, see https://github.com/C2MA-workshop/c2ma-tutorials
