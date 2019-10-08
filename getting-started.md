
- Getting Started: A Novella
Last updated 10/7/19

- Repo Setup:
  
  - Note: NOT recommend for devs to use React Native Debugger. It will be too slow. We have our own system of logging in the console that works great!
  - Note: The repo on GitHub is called phd-mobile.
  
  1. Create a GitHub account with your yum email. This is the email that will get the invite to our internal repos. Teams message     Stephen Miller with your new GitHub account info and he will add you.
  2. Install Xcode and Android Studio following the directions on the React Native docs. We do not use Expo, so use React Native Cli instructions.
  3. You need to create a personal token in Github. Go to Settings -> Developer Settings -> Personal Tokens to make one.
  4. Fork repo. Use your username + the personal token as the password. Directions for this are below in the Forked Repos section.
  5. Install nvm (node version manager). Realm (a dependency in our project) does not like new node. You need 10.13.0 for a good time. You can do this by going here and following the instructions for installation: https://github.com/nvm-sh/nvm
  6. Switch node versions to 10.13.0.
  7. Type ‘yarn’ and press enter to install all the goods.
  8. If your Xcode can’t find a simulator, go to Xcode -> Preferences -> Components and install some.
  9. Check the Origin branch. Type ‘git remote -v”. If you don’t see an Origin which contains the original repo, you’ll need to do the following:
	  a. Type ‘git remote set-upstream https://github.com/pizzahutdigital/phd-mobile.git’
	  b .Press enter
	  c. Check the upstream with ‘git remote -v” and make sure there’s an origin.
  10. Run ‘react-native run-ios’ to get moving!
  11. In another terminal window, use ‘yarn startLog’. (this is to yarn start + start our logging!)
  12. In the simulator, Cmd + D and select “debug remotely” and you’ll be able to see the logging in the console.
  
  Now that you have the app running, we need to set up your accounts for each env (prod / staging).
  13. Create an account from the main screeno of the app. (recommended that you use your yum email).
  14. Log out and log back in.
  15. Go to Account -> Debug and see what environment is selected. If staging, then you are using your staging account and prod if your are using your prod account. Let’s make the other account for the other environment. Select the environment you do not have an account for under Environment Selected and then log out. Create an account again. Now you have both accounts. Every time you need to switch environments, choose the environment and then make sure you log out and back in with the right account.
  
  
  
  - Forked Repos: How to Fork & Work With a Fork
    We do not work directly with our ph repo (unless we are merging our completed code). 
    We work from FORKS of the repo.
    
    1. Getting a fork from a repo:
      Go to the repo: phd-mobile
      Click the Fork button at the top and head over to the new fork of the repository on your account.
      Clone the repo on your account.
    
    2. Now that you have the repo forked and local, you need to set the upstream:
      Type ‘git remote -v” and press enter. You’ll notice that we have an origin (your fork) but no upstream.
      Type ‘git remote add upstream the_phd-mobile_repo_url’ and press enter
      To check that you now have the upstream branch, type ‘git remote -v’. There will an upstream now.
   
    3. Updating a forked repo:
      If there are changes in the origin repo and you need them locally, just use 'git fetch upstream’ command.
      Then go to your branch you want to update with ‘git checkout branch_name’
      Then you can merge the two branches with ‘git merge upstream/branch_name’
      If you want to update your personal fork on GitHub, you need to make sure to push your changes!
  
  
  - Fun Facts / Useful Info:
    Two environments: prod and staging
    
    If you run the project in Xcode, it will be in PROD env. Use command line to start the app for STAGING. You can see what env you are in @ Account -> Debug in the app.
    
    Test store #: 000006 — go bananas at this store! Make all the orders! Do all the things!
    
    The files within /js/phd are the newer ones.
