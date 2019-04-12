# How to setup some sub accounts 

1. First, Sign into your AWS account. 
2. Search for IAM in the services search bar. 
3. Click on IAM and then click on Users on the side bar. 
4. Next click on the Add user button. 
5. Give this new User a username and decide what type of access you will grant the user. Click on the next button below.
    * For access through the AWS CLI(terminal) you would only need *Programmatic access*
6. Next you must set the users permissions. You can click on *Attach existing policies directly* to avoid having to define your own permissions. 
7. Choose the correct policy for the user and hit next.
8. You can skip over tags. Hit next.
9. A review page will be visible on the screen. Look over the new users details and when ready hit Create user.
10. The Next page will have a *Download.csv* button. This file will contain all of the users credentials. You can send this file to your developer who will gain access through this account. 

# As the New User
You want to be able to access someones amplify project. Heres how. 

## For programatic access 
1. Make sure you have cloned the repository of the project you want to access. 
2. Make sure you have the credential file that was given to you by the main user of the AWS account. 
3. Open the credentials file and put it aside for now. 
4. Open a terminal and make sure you go to the root directory of your repository. 
    * For the next part you will need to have amplify-cli installed on your system and also dont forget to run `npm install` in the root directory before continuing 
5. In the root directory run : `amplify configure`
6. If a browser window opens you can close it and hit enter in the terminal to continue.
7. Next, the terminal will ask you to select a region. double check with your administrator(person who gave you the user credentials) to check the region that his AWS account is in. 
8. After selecting the region, you will be asked to supply a username. This is when you enter the username that is located in the credentials file. Hit enter when done. 
9.  Once again the browser window might open, close the window and hit enter in the terminal.
10. The terminal will ask for an access key. In the credential file there will be an access key. copy it and paste it into the terminal and hit enter. 
11. The terminal will then ask for a secret access key. You can find you secret key in the credentials file. copy and paste it into terminal and hit enter. 
12. Lastly, the terminal will ask you to enter a profile name. This will be local to your machine you can enter what ever name you wish. Hit enter when done. 
13. The `amplify configure` setup is done. 
14. In the same terminal type `amplify init`. 
15. You will be asked if you want to use an existing environment. Type `Y` and Select the environment that you will be working in. The administrator of the AWS account will have created an environment. Ask them for the name or which one to select from the list. 
16. After selecting the environment, choose the default editor of your choice. Hit enter
17. Then the terminal will ask if you want to use an AWS profile. This is the profile that was created in the previous step. Type `Y` and hit enter. 
18. Select your profile and hit enter. 
19. The terminal will printout 
> > Initialized your environment successfully.

> > Your project has been successfully initialized and connected to the cloud! 
20. If you have a cognito pool ask your Administrator to send you a copy of their aws-export file. Save this file in the src directory of your project.
21. You should now be able to access the user pool through cognito and use the Authentication library supplied by Amplify. 