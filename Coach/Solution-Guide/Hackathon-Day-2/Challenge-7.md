# Challenge 07: Enhancing Contoso Traders with GitHub Copilot

## Introduction

Contoso Traders is an e-commerce web application. In this challenge, as a DevOps engineer, your focus is to seamlessly implement and test new features with Copilot, ensuring accuracy and alignment. Conduct a thorough code review and enhance security using GitHub Advanced Security's CodeQL. Streamline development with a GitHub Actions CI/CD pipeline for Contoso Traders, ensuring efficient and secure deployment.

This is the solution guide that contains all of the comprehensive, step-by-step directions needed to finish the challenge.

## Accessing the Azure Portal

1. To access the Azure Portal, open the Edge browser from inside the environment and navigate to the **[Azure Portal](https://portal.azure.com)**.

1. On the **Sign in to Microsoft Azure** tab, you will see a login screen. Enter the following email/username, and then click on **Next**. 
   * **Email/Username**: <inject key="AzureAdUserEmail"></inject>
        
1. Now enter the following password and click on **Sign in**.
   * **Password**: <inject key="AzureAdUserPassword"></inject>
     
1. If you see the pop-up **Stay Signed in?**, click No.

1. If you see the pop-up **You have free Azure Advisor recommendations!**, close the window to continue the lab.

1. If a **Welcome to Microsoft Azure** pop-up window appears, click **Maybe Later** to skip the tour.

## Solution Guide

## Exercise 1: Integrate an 'About Us' app component in React using GitHub Copilot

### Task 1: Sign in to GitHub Copilot in Visual Studio Code

1. Open **Visual Studio Code** from the desktop screen. 

   ![Picture1](../media/cl7-ex1-t1-s1.png)
   
1. At the bottom right corner, click on **Sign in to GitHub** prompt that appears.

   ![Picture1](../media/cl7-ex1-t1-s2.png)

1. Next, once you get the popup, click on **Allow**.

   ![Picture1](../media/cl7-ex1-t1-s3.png)

1. In the sign-in to GitHub page in edge browser, enter the **GitHub UserEmail** and **GitHub Password** and click on **Sign in**.

   ![Picture1](../media/cl7-ex1-t1-s4.png)

   >**Note:** Navigate to the **Environment** tab to view the key-value pairs of the **GitHub UserEmail**, and **GitHub Password**. You can use the copy buttons under the actions column to have the values copied instantly. Alternatively, it is suggested to have the values copied over onto a notepad for easy accessibility. 

   ![](../media/cl7-ex1-t1-s4-b.png)

1. Next, to get the authentication code, sign in to Outlook in the Lab VM through an **InPrivate** window (https://outlook.office365.com/mail/)
with the github credentials that were copied over to Notepad in the previous step. After logging into Outlook within the Lab Virtual Machine, locate the most recent email that contains the verification code, and then select **Verify** to return to the login screen.

   >**Note:** The email containing the verification code can sometimes creep into the archive/spam folders within your Outlook.

   ![Picture1](../media/cl7-ex1-t1-s5.png)

1. Next, click on **Authorize Visual-Studio-Code** to provide additional permissions to GitHub for VS Code on the following page if asked for, as shown in the screenshot below:

   ![Picture1](../media/cl7-ex1-t1-s6.png)

1. You will encounter a pop-up prompt. Click **Open** to proceed.

   ![Picture1](../media/cl7-ex1-t1-s7.png)
   
   >**Note:** If you get another pop-up stating **Allow an extension to open this URI**, please click on **Open**.

1. You will be able to see in the bottom right corner that Github Copilot has been activated.

   ![Picture1](../media/cl7-ex1-t1-s8.png)

   >**Note:** If the activation status of Github Copilot in the bottom right corner is not visible, try restarting Visual Studio Code to ensure that the activation status becomes visible in that location.

1. Verify if **GitHub Copilot Chat** is installed. If its installed, the below icon should appear in the left navigation pane.
   
    ![Picture1](../media/cl7-ex1-t1-s9.png)
   
### Task 2: Integrate an 'About Us' app component in React using GitHub Copilot

  >**NOTE:** It should be noted that the code suggestions offered by GitHub Copilot might not exactly match the screenshots shown within the labguide. GitHub Copilot is an AI-powered tool that generates code based on context and patterns, and its suggestions can be influenced by various factors. It is also important that you have the knowledge on operating and running React Applications which may be needed as you proceed with this exercise.

1. In a new Visual Studio Code window, go to **Explorer (1)** and click on **Open Folder (2)**. Navigate to **C:\Workspaces\lab\DevOps-DevSecOps-Hackathon-lab-files-2/** within the file explorer, and then select the **ContosoTraders.Ui.Website.V2.Raw** folder.

    ![Picture1](../media/openfolders.png) 

2. Ensure to click on **Yes, I trust the authors** within the pop-up to successfully import the CloudLabs folder into VS Code.

   ![Picture1](../media/trust-authors.png)

3. Once the project has loaded, within the explorer pane of VS Code, navigate to `Contosotraders.Ui.Website.V2\src` folder to view the `App.js` file.

   ![Picture1](../media/CL7-EX1-T2-S3.png)

4. Within the **CHAT: GITHUB COPILOT** pane, type: `Help me create the new About Us" page in ContosoTraders.Ui.Website.V2\src` and observe the AI response. You can follow the instructions provided by GitHub Copilot towards successfully adding the About Us page as a part of the sample React application that you have imported into VS Code.

   ![Picture1](../media/CL7-EX1-T2-S4.png)

  >**Disclaimer:** It should be noted that the code suggestions offered by GitHub Copilot might not exactly match the screenshots shown within the labguide. GitHub Copilot is an AI-powered tool that generates code based on context and patterns, and its suggestions can be influenced by various factors. It is also important that you have the knowledge on operating and running React Applications which may be needed as you proceed with this exercise.

  >**Note:** However the ease of executability of this challenge, you can open a new folder within VS Code and import the solution folder from the Windows file explorer with path, `C:\Workspaces\lab\DevOps-DevSecOps-Hackathon-lab-files-2\`. Select the **src** folder. This solution project has integrated "About Us" page and unit test cases for the same.

  >**Note:** If you wish to continue to manually edit the raw project, follow the steps from step 6.

5. Create a new file named `AboutUs.css` **(1)** in your `src` directory ie., within the path `ContosoTraders.Ui.Website.V2\src` and then add the following code **(2)**:

   ```
   .about-us {
       padding: 20px;
       font-size: 1.2em;
       line-height: 1.6;
       color: #333;
   }
   
   .about-us h1 {
       font-size: 2em;
       margin-bottom: 0.5em;
   }
   ```

   >**Note:** This `AboutUs.css` file contains CSS (Cascading Style Sheets) rules that are used to style HTML elements on a webpage. The specific code you've selected defines styles for elements with the class `about-us` and `h1` elements within elements with the class `about-us`.

   ![Picture1](../media/CL7-EX1-T2-S5.png)

6. Save the newly created `AboutUs.css` file.

7. Now let's build a new component for the application. Create a new file named `AboutUs.js` **(1)** in your `src` directory ie., within the path `ContosoTraders.Ui.Website.V2\src` and then add the following code **(2)**:

   ```
   import React from "react";
   import "./AboutUs.css";
   
   function AboutUs() {
     return (
       <div className="container">
         <div className="about-us">
           <h1 className="text-center">About Us</h1>
           <p>
             Contoso Traders is a leading company in the trading industry. We have
             been serving our customers for over 20 years with high-quality
             products and excellent customer service.
           </p>
           <p>
             Our team is dedicated to providing the best service possible. We value
             our customers and strive to meet their needs.
           </p>
         </div>
       </div>
     );
   }
   
   export default AboutUs;
   ```

   >**Note:** Free free to make changes in the above code snippet as per your use case scenario.

   >**Note:** Notice that the css rules have been imported into the `AboutUs.js` file using the code, `import "./AboutUs.css";`.
   
   >**Note:** The `AboutUs.js` file is a React component that renders an "About Us" section on a webpage based on the CSS rules that have been defined in `AboutUs.css` file.

8. Save the newly created `AboutUs.js` file.

9. Now navigate to the `App.js` file to integrate the "About Us" page that was created in the previous steps.

10. Within the `App.js` file, enter the following code.

     ```
     import AboutUs from "./AboutUs";
     import "./App.css";
     ```

11. Your `App.js` should look similar like the below screenshot:

     ![Picture1](../media/CL7-EX1-T2-S11.png)

12. Scroll down to the end of the code within the `App.js` file and then add the following code to include the newly created `About Us` component.

     ```
     <AboutUs />
     ```
13. Your `App.js` should now look similar like the below screenshot:

     ![Picture1](../media/CL7-EX1-T2-S13.png)

14. To run your React application, you typically use the command line (also known as the terminal). Here are the steps:
      - Within Visual Studio Code, you can open the terminal by going to the top menu to click on **Terminal** **(1)** and then select **New Termimal (2)**.
      - Navigate to your project directory. You can do this with the `cd` command followed by the path to your project. You can use the below command to navigate to the React application's working directory **(3)**:
      ```
      cd C:\Workspaces\lab\DevOps-DevSecOps-Hackathon-lab-files-2\src\ContosoTraders.Ui.Website.V2
      ``` 
      - Once you're in your project directory, you can start the application with the `npm start` **(3)** because we need npm to create the Contoso Traders Application. After running the following command within the terminal, your application should start, and you can view it in your web browser at http://localhost:3000.
        
      ```
      npm run start
      ```
      
     ![Picture1](../media/CL7-EX1-T2-S14.png)

    >**Note:** If the above command fails, you might need to run the following command :

     ```powershell
     npm i
     ```
   
     - The command `npm i` is a shorthand version of `npm install`. It is used in Node.js environments to install all the dependencies listed in the `package.json` file. These dependencies are libraries or packages that your project needs to run correctly. The installed packages will be placed in a folder named `node_modules` in your project directory.

     - After the installation of all the dependencies, execute the command - `npm run start` to start the application. This open a new browser tab over the url path, `http://localhost:3000/`.

15. Observe that the new "About Us" component has been added at the end of the webpage.

     ![Picture1](../media/CL7-EX1-T2-S15.png)

## Exercise 2: Generate and run Unit Test cases using GitHub Coplilot:

### Task 1: Create and run test cases:

1. In Visual Studio Code, go to **Explorer** and navigate to path `ContosoTraders.Ui.Website.V2\src\components` and open the `WelcomePopup.js` file.

   ![Picture1](../media/CL7-EX2-T1-S1.png)

2. Select all code lines `[CTRL+A]` of `WelcomePopup.js` file **(1)** and then paste the following prompt **(2)** within the GitHub Copilot Chat Panel and press enter:
   ```
   /tests
   ```

   ![Picture1](../media/CL7-EX2-T1-S2.png)

3. Now create a new file named `WelcomePopup.test.js` under the path `ContosoTraders.Ui.Website.V2\src\components`.

   ![Picture1](../media/CL7-EX2-T1-S3.png)

4. Navigate back to the GitHub Copilot chat panel and copy the unit test that has been generated using Copilot for the `WelcomePopup` component. Ensure to paste these unit test cases within the newly created file - `WelcomePopup.test.js` under the `components` folder and save the file.

   **Disclaimer:** Please be aware that the unit test cases produced by GitHub Copilot may not be accurate. There could be issues within the test cases, such as lacking code logic. It's advisable to thoroughly review the generated code before integrating it into your project.

   **Note:** Below is an example unit test cases generated by GitHub Copilot which upon running leads to successful test case passes. This following unit test file is being provided for the easy execution using the `react-app/jest` framework.
   
   ![Picture1](../media/CL7-EX2-T1-S4-a.png)

   ![Picture1](../media/CL7-EX2-T1-S4-b.png)

5. Once ready with the test cases, open a new terminal within Visual Studio Code, and navigate to the following path/directory by running the below command within the terminal:

   ```
   cd C:\Workspaces\lab\DevOps-DevSecOps-Hackathon-lab-files-2\src\ContosoTraders.Ui.Website.V2\src\components
   ```

   >**Note:** Ensure that your current working directory within the terminal has the `components` folder in its present path. In this scenario, the `components` folder is present inside the `/src` directory. 

6. To execute the unit test cases genereated by GitHub Copilot, we need to run the `WelcomePopup.test.js` file using the following command within the terminal:

   ```
   npm run test
   ```

7. Post execution of the above unit test, you must ensure to have a successful - `PASS` test runs with no errors. If you are produced with errors, please understand the intricacies of the error as mentioned within the terminal and work towards a successful unit test run.

   ![Picture1](../media/CL7-EX2-T1-S7.png)

## Exercise 3: Code Review and Security Check

### Task 1: Submit Codebase Modifications to GitHub Repository

1. In a new browser tab, open ```https://www.github.com/login```. From the **Environment Details** page **(1)**, navigate to **License** **(2)** tab and **copy** **(3)** the credentials. Use the same username and password to log into GitHub.

   ![](../media/dev2.png) 

2. once logged-in, on the upper-right corner, expand the user **drop-down menu** **(1)** and select **Your repositories** **(2)**.

   ![The `New Repository` creation form in GitHub.](../media/2dg1.png "New Repository Creation Form")

3. Next to the search criteria, locate and select the **New** button.

   ![The `New Repository` creation form in GitHub.](../media/ex2-t3-3-git.png "New Repository Creation Form")

4. On the **Create a new repository** screen, name the repository ```devsecops-2``` **(1)**, select **Public** **(2)**, and click on the **Create repository** **(3)** button.

   ![](../media/CL7-EX3-T1-S4.png) 

5. On the **Quick setup** screen, copy the **HTTPS** GitHub URL for your new repository and **save it** in a notepad for future use.

   ![](../media/CL7-EX3-T1-S5.png)

6. From the GitHub username, note down the **Unique-ID** present in the Username. You'll need this in the upcoming steps.

   ![](../media/cl1-t1-s13.png)

7. Navigate back to the **Visual Studio Code** application in which the terminal is already open. In the terminal, click on the **drop-down** button and select **PowerShell** to open a fresh PowerShell terminal tab.

   ![imported-Quick setup screen is displayed with the copy button next to the GitHub URL textbox selected.](../media/2dg4.png "Quick setup screen")

8. In Visual Studio Code, run the below commands in the terminal to set your **email** and **username**, which Git uses for commits. Make sure to replace the GitHub account email and username.
   
     ```pwsh
     cd C:\Workspaces\lab\DevOps-DevSecOps-Hackathon-lab-files-2\src\ContosoTraders.Ui.Website.V2
     git config --global user.email "you@example.com"
     git config --global user.name "Your UserName"
     ```
     
   ![](../media/cl1-t1-s15.png) 
     
    Run the below-mentioned command in the terminal. Make sure to replace `your_github_repository-url` with the value you copied in step 5 and `Unique-ID` in step 6.

    Note: This step is done to initialize the folder as a Git repository, commit, and submit contents to the remote GitHub branch “main” in the lab files repository created named `devsecops`. 

      ```pwsh
      git init
      git add .
      git commit -m "Initial commit"
      git branch -M main
      git remote add origin<Unique-ID> <your_github_repository-url>
      git push -u origin<Unique-ID> main
      ```
     
   - If you are asked to authenticate your GitHub account, select **Sign in with your browser**, and you will be prompted with a pop-up window to authorize Git Credential Manager. Click on **Authorize git-ecosystem** to provide access.

       ![](../media/ex2-t3.png)
       
   - After you are prompted with the message **Authorization Succeeded**, close the tab and continue with the next task.

### Task 2: Implement Code Scanning and CodeQL

In this task, you'll configure Code scanning and explore CodeQL alerts. Code scanning is a feature that you use to analyze the code in a GitHub repository to find security vulnerabilities and coding errors. Any problems identified by the analysis are shown on GitHub.

**Note**: To perform this task, the GitHub repository should be public. If the repository visibility is private, please go to the settings of the repository and change the visibility to public.

1. Login to GitHub where the `devsecops-2` repository was created.

2. Select the **settings** ***(1)*** tab from the GitHub browser tab. Click on **code security and analysis** ***(2)*** under the security side blade.

   ![](../media/2dgn168.png)  

3. Click on the **Set up** **(1)** button to enable CodeQL analysis, and select the **Advanced** **(2)** option for creating a CodeQL Analysis YAML file.

   ![](../media/2dgn169.png)   

4. Update the workflow name to **codeql-analysis.yml** ***(1)*** and review the yaml file. Select **Commit changes** ***(2)***, then select **Commit directly to the main branch** ***(3)***, and click on **Commit new file** ***(4)***.
  
   ![](../media/cl2-t1-s3.png)

   ![](../media/ex5-task1-step3b.png) 

5. Navigate to the **Actions** ***(1)*** tab, here you can review the **workflow** ***(2)*** run.
    
   ![](../media/cl2-t1-s4.png) 

6. Navigate to the **Security** ***(1)*** tab and click on **View alerts** ***(2)***.
   
   ![](../media/cl2-t1-s5.png)

7. You will be navigated to the **Code scanning** section. You'll be able to visualize the **No code scanning alerts here!**.
   
   ![](../media/cl2-t1-s6.png)

### Task 3: Implement Repository security advisories

In this task, you'll enable Repository security advisories. You can use GitHub Security Advisories to privately discuss, fix, and publish information about security vulnerabilities in your repository. Anyone with admin permissions to a repository can create a security advisory.

1. Navigate to the **Security** ***(1)*** tab, select **Advisories** ***(2)*** from the side blade, and click on **New draft security advisory** ***(3)***.

   ![](../media/cl2-t2-s1.png)

2. In the Open a draft security advisory tab, under the Advisory Details section, provide the following details:

   - Title: **Improper Access Control in devsecops-2/src/App.js** ***(1)***
   - CVE identifier: **Request CVE ID later** ***(2)***
   - Description: **Add** ***(3)*** the below-mentioned details in the description section.
   
   ```
   Impact
   What kind of vulnerability is it? Who is impacted?

   HTTP request handlers should not perform expensive operations such as accessing the file system, executing an operating system command, or interacting with a database without limiting the rate at which requests are accepted. Otherwise, the application becomes vulnerable to denial-of-service attacks where an attacker can cause the application to crash or become unresponsive by issuing a large number of requests at the same time.

   Patches
   Has the problem been patched? What versions should users upgrade to?

   It is patched and rectified the error. Please use 1.2 version

   Workarounds
   Is there a way for users to fix or re../mediate the vulnerability without upgrading?

   // set up rate limiter: maximum of five requests per minute
   var RateLimit = require('express-rate-limit');
   var limiter = new RateLimit({
   windowMs: 1601000, // 1 minute
   max: 5
   });

   // apply rate limiter to all requests
   app.use(limiter);

   Added the above code in app.js

   References
   Are there any links users can visit to find out more?

   https://github.com/OWASP/API-Security/blob/master/2019/en/src/0xa4-lack-of-resources-and-rate-limiting.md
   https://codeql.github.com/codeql-query-help/javascript/js-missing-rate-limiting/
   ```
    
   ![](../media/CL7-EX3-T3-S2.png)

3. In the **Affected products** section, provide the following details and click on **Create draft security advisory** ***(7)***   
 
   - Ecosystem: **composer** ***(1)***
   - Package name: **devsecops-2/src/App.js** ***(2)***
   - Affected version: **<1.2** ***(3)***
   - Patched version: **1.2** ***(4)***
   - Severity: **High** ***(5)***
   - Common Weakness Enumerator (CWE): **Improper Access Control (CWE-284)** ***(6)***
  
   ![](../media/CL7-EX3-T3-S3.png)

4. Once the security advisory is created, scroll down and click on **start a temporary private fork**. It is used to collaborate on a patch for this advisory.

    ![](../media/CL7-EX3-T3-S4-a.png)
    
    ![](../media/cl2-t2-s4-b.png)

5. After having the temporary fork, you can request a CVE. It is used for GitHub reviews and published security advisories. Upon review, we may use this advisory to send Dependabot alerts to affected repositories and redistribute the advisory through our API and Atom feed.

## Exercise 4: CI/CD Pipeline Setup and infrastrucure Deployment

### Task 1: Deploy Infrastructure

1. Login to your Azure portal wih the credentials provided in the **Environment Details** tab of the integrated CloudLabs Environment.

2. In the global search bar, search for and select **Static Web Pages**

3. Click on **+ Create** to create a new Static Web App.

4. In the **Basics tab** of the **Create Static Web App** page, enter the following details:
   - **Subscription:** Select the available subscription **(1)**.
   - **Resource Group:** Create a new resource group named - **Static-Web-App (2)**.
   - **Name:** `React-Static-Web-App` **(3)**.
   - **Plan type:** Select **Free (4)**.
   - **Region for Azure Functions API and staging environments:** Select **East US 2 (5)**.
   - **Source:** Select **GitHub (6)**
   - **GitHub account:** Connect to your GitHub account which has the `devsecops-2` repository with tehe React application files **(7)**.
   - **Organization:** Select your assigned Github organization **(8)**.
   - **Repository:** Select `devsecops-2` **(9)**.
   - **Branch:** `Main` **(10)**.
   - **Build presets:** Search for and select **React (11)**.
   - **App location:** `/` **(12)**.

      >**Note:** `/` refers to the root directory of the GitHub repository. Ensure that the location is specified appropriately as per your GitHub file structure.
   
   - Leave the other fields at default and then click on **Review + Create (13)**.
   - Finally, click on **Create** on the **Review + create** page to create the static web app.

    ![](../media/CL7-EX4-T1-S4.png)
   
    ![](../media/CL7-EX4-T1-S4-b.png)

5. Once the deployment is successful, click on **Go to resource**.

    ![](../media/CL7-EX4-T1-S5.png)

6. Navigate back to your `devsecops-2` repository on the GitHub portal and click on the **Actions** tab.

    ![](../media/CL7-EX4-T1-S6.png)

7. Ensure that your **Azure Static Web Apps CI/CD** workflow has a successful run status.

    ![](../media/CL7-EX4-T1-S7.png)

8. Navigate back to your Azure portal on the overview page of the recently created Static Web App and click on the **URL**

    ![](../media/CL7-EX4-T1-S8.png)

9. The URL redirects you to a new browser tab with the React Application up and running.

    ![](../media/CL7-EX4-T1-S9.png)

10. Click on **Get Started** and scroll down within your static web app to view the integrated **About Us** page.

    ![](../media/CL7-EX4-T1-S10.png)

## Success criteria:
To complete this challenge successfully:

- Successful implementation of the new feature.
- Accuracy and completeness of the generated unit tests with all successful passes.
- Successful setup and execution of the CI/CD pipeline.

## Additional Resources:

- Refer to [About GitHub Copilot Chat](https://docs.github.com/en/copilot/github-copilot-chat/about-github-copilot-chat) for reference.
- Refer to [Copilot Chat writes Unit Tests](https://dev.to/this-is-learning/copilot-chat-writes-unit-tests-for-you-1c82) for reference.
- Refer to [Using GitHub Copilot Chat in your IDE](https://docs.github.com/en/copilot/github-copilot-chat/using-github-copilot-chat-in-your-ide) for reference.
