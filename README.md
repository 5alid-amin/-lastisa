# -lastisa
last in shaa allah
In the clickonce installer Follow the following steps:

If your project isn't on github, create a repository and push your code there. It has to be public.
On your computer, create a folder called 'published' in the root of your repository. Make sure this folder is not ignored in the .gitignore
Create a file called .gitattributes in this /published folder. Add the following contents
*.manifest binary
*.application binary
*.deploy binary
*  -text
How commit and push to the github repository. Navigate to this file in the repository click on the RAW button. Copy the URL address till '/publish/'. It will look like this
https://raw.githubusercontent.com/{your-account-name}/{your-repo-name}/{branch}/published/
In the clickonce installer enter the following paths
Publish Path: {repo-path}/pubhished
Install Path: https://raw.githubusercontent.com/{your-account-name}/{your-repo-name}/{branch}/published/ This the the server address from where the setup will install your application from.
Update Path: https://raw.githubusercontent.com/{your-account-name}/{your-repo-name}/{branch}/published/ This the the server address from where the setup will check for updates.
NOTE: Use this link to navigate through the clickonce installer:
https://docs.microsoft.com/en-us/visualstudio/deployment/quickstart-deploy-using-clickonce-folder?view=vs-2022.
Make sure the check the 'Create Desktop Shortcut' option before publishing. Now commit and push your code.
Now in the /published folder click on the setup to install the application. This will connect the the github servers to download and install the required files on your computer in the directory C:\Users\vib28\AppData\Local\Apps\2.0.
To publish an update for the application follow these steps
Make the changes to your c# applicaiton.
Publish the application again (to the same folder /published). The revision number should increase, and there should be a new folder added to the location /published/Application Files
Commit and push your code to github. Now the raw files have been updated. So whenever the client runs his application, it will automatically prompt for downloading the update.
