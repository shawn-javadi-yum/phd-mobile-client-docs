
Getting Started: A Novella
Last updated 10/10/19

Repo Setup:
  
  1. Create a GitHub account with your yum email. This is the email that will get the invite to our internal repos. Teams message Stephen Miller with your new GitHub account info and he will add you.

  2. Install Xcode and Android Studio following the directions on the [React Native docs](https://facebook.github.io/react-native/docs/getting-started). We do not use Expo, so use React Native Cli instructions on that page to install.

  3. You need to create a personal token in Github. Go to Settings -> Developer Settings -> Personal Tokens to make one.

  4. Fork the repo. The repo is [phd-mobile](https://github.com/pizzahutdigital/phd-mobile). Use your username + the personal token as the password.

  5. Getting a fork from a repo:
      Go to the repo: [phd-mobile](https://github.com/pizzahutdigital/phd-mobile)
      Click the Fork button at the top and head over to the new fork of the repository on your account.
      Clone the repo on your account.

  6. Now that you have the repo forked and local, you need to set the upstream:
      Type ‘git remote -v” and press enter. You’ll notice that we have an origin (your fork) but no upstream.
      Type ‘git remote add upstream https://github.com/pizzahutdigital/phd-mobile' and press enter.
      To check that you now have the upstream branch, type ‘git remote -v’. There will an upstream now.

  7. Navigate to the cloned repo and run 'yarn install'.

  8. If yarn install is not working properly, and you see mention of 'realm' in the error output, it is probably your node version. Install nvm (node version manager). You can do this by going [here](https://github.com/nvm-sh/nvm) and following the instructions for installation. Once done, switch node versions to 10.13.0 and continue.

  9. If your Xcode can’t find a simulator, go to Xcode -> Preferences -> Components and install some.

  10. Check the Origin branch. Type ‘git remote -v”. If you don’t see an Origin which contains the original repo, you’ll need to do the following:
	  a. Type ‘git remote set-upstream https://github.com/pizzahutdigital/phd-mobile.git’
	  b .Press enter
	  c. Check the upstream with ‘git remote -v” and make sure there’s an origin.

  11. Run ‘react-native run-ios’ to get moving!

  12. In another terminal window, use ‘yarn startLog’. (this is to yarn start + start our logging!)

  13. In the simulator, Cmd + D and select “debug remotely” and you’ll be able to see the logging in the console.
  
  Now that you have the app running, we need to set up your accounts for each env (prod / staging).

  14. Create an account from the main screeno of the app. (recommended that you use your yum email).
  
  15. Log out and log back in.

  16. Go to Account -> Debug and see what environment is selected. If staging, then you are using your staging account and prod if your are using your prod account. Let’s make the other account for the other environment. Select the environment you do not have an account for under Environment Selected and then log out. Create an account again. Now you have both accounts. Every time you need to switch environments, choose the environment and then make sure you log out and back in with the right account.
  
  
  
Forked Repos: How to Fork & Work With a Fork

  We do not work directly with our ph repo (unless we are merging our completed code). 
  We work from FORKS of the repo.
  
  1. Getting a fork from a repo:
    Go to the repo: [phd-mobile](https://github.com/pizzahutdigital/phd-mobile)
    Click the Fork button at the top and head over to the new fork of the repository on your account.
    Clone the repo on your account.
  
  2. Now that you have the repo forked and local, you need to set the upstream:
    Type ‘git remote -v” and press enter. You’ll notice that we have an origin (your fork) but no upstream.
    Type ‘git remote add upstream https://github.com/pizzahutdigital/phd-mobile)’ and press enter
    To check that you now have the upstream branch, type ‘git remote -v’. There will an upstream now.
  
  3. Updating a forked repo:
    If there are changes in the origin repo and you need them locally, just use 'git fetch upstream’ command.
    Then go to your branch you want to update with ‘git checkout branch_name’
    Then you can merge the two branches with ‘git merge upstream/branch_name’
    If you want to update your personal fork on GitHub, you need to make sure to push your changes!
  
  
Fun Facts / Useful Info:

  - Two environments: prod and staging
  
  - If you run the project in Xcode, it will be in PROD env. Use command line to start the app for STAGING. You can see what env you are in @ Account -> Debug in the app.
  
  - Test store #: 000006 — go bananas at this store! Make all the orders! Do all the things!
  
  - The files within /js/phd are the newer ones.

  - It is NOT recommend for devs to use React Native Debugger. It will be too slow. We have our own system of logging in the console that works great!

  - Why we are using an older version of Node: Realm does not play well with the new node. Using an older version allows us to yarn install without issue.
