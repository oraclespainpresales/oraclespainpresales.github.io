# Oracle Visual Builder - Basic
## Understanding the basics of Visual Builder

### Purpose of the lab

This lab will introduce Oracle Visual Builder, explain the main components and allow you to build your first Visual Builder Web app.

For advanced topics, you can go to the Advanced lab

### Introducing Oracle Visual Builder

Oracle Visual Builder is a visual and declarative cloud environment for **LowCode** developing and hosting engaging mobile and web applications.

Oracle Visual Builder provides easy access to data from any REST-based service, and enables the creation of custom reusable business objects for storing and managing data. Using the cloud-based visual development tools, you can create and test responsive web applications and native mobile apps without the need to install any additional software. The visual designer enables you to quickly layout pages in your applications by dragging and dropping UI components, customizing their attributes and defining their behavior.

While Oracle Visual Builder provides a rich set of visual designers to enhance productivity, experienced developers always have access to the source code of their applications. Developers can enhance their application’s functionality using the code editors to write custom JavaScript functions and edit application metadata.

Oracle Visual Builder leverages the open source Oracle JavaScript Extension Toolkit ([Oracle JET](https://www.oracle.com/webfolder/technetwork/jet/index.html)) to create engaging web and mobile interfaces. The reusable Oracle JET Web Component architecture, built based on the Web Component standard, can be added to the application to further enhance the user experience.

### Request your Oracle Cloud free trial account

Oracle offers free trials to try any of our Cloud services (including Visual Builder!). To perform the steps in this tutorial, you must have an active subscription to Oracle Cloud Infrastructure or a [Free Trial Account](https://www.oracle.com/cloud/free/).

Please follow these steps to get your own trial account:

1.  Go to [https://www.oracle.com/cloud/free/](https://www.oracle.com/cloud/free/) and click the _Start for free_ button:

    ![](workshops/visualbuilder/media/01.png)

2.	Select your home territory and enter the email address **that you have used to register to this Workshop**, so that you get the 400€ of free Universal Credits:

    ![](workshops/visualbuilder/media/02.png)

3.  After clicking _Next_, you **must** get a popup message similar to this one:

    ![](workshops/visualbuilder/media/03.png)

    If you don’t get it, **do not go ahead with the subscription**. Let us know through ZOOM Q&A if you’re live in the session and provide the right email address for us to get it whitelisted and get your training promotion of free Universal Credits.

4.  Enter your personal information in the next form. You can select either Personal or Company use for _Account Type_. Type in your _Cloud Account Name_, which must be unique across all Oracle Cloud. Select your Home Region mainly based on your geographic location. Take into account that trial accounts like this one, will NOT allow you to subscribe to other Oracle Cloud regions (with paid accounts you can subscribe to any region you want, without any additional cost) nor changing it afterwards.

    You may want to review first the Cloud Services available on each one [here](https://www.oracle.com/cloud/data-regions.html) before selecting _Home Region_.

    If you’re located in Europe, we suggest to use Frankfurt, Amsterdam or London.

5.	Enter the password you will use later for Cloud login.

6.	Click on _Review Terms and Conditions and Complete Sign-Up_

7.	Review your email INBOX. You will receive two separate mails. Wait until you receive a message with the subject “**Your Oracle Cloud Account is Fully Provisioned”** as follows:

    ![](workshops/visualbuilder/media/04.png)

8.	Click the _Sign In to Oracle Cloud_ button to get logged to Oracle Cloud with the username (email used) and password.

### Setting up your new trial account for the Oracle Visual Builder workshop

Your brand new Oracle Cloud Trial account is ready but you haven't yet created all the services/artifacts needed for the workshop. Follow the next steps to get ready:

1.  If not yet logged in, go to the Oracle Cloud console URL: `https://console.your_region.oraclecloud.com/` where `your_region` is the home region selected during the trial request in step 4 above. For example:

    | Home Region   | Console URL                                     |
    | ------------- |-------------------------------------------------|
    | Frankfurt     | https://console.eu-frankfurt-1.oraclecloud.com/ |
    | Amsterdam     | https://console.eu-amsterdam-1.oraclecloud.com/ |
    | London        | https://console.uk-london-1.oraclecloud.com/    |

    For other Home regions check [here](https://docs.cloud.oracle.com/en-us/iaas/Content/GSG/Tasks/signingin.htm)

2.  Make sure you use the Single Sign-On (SSO) option by clicking _Continue_:

    ![](workshops/visualbuilder/media/05.png)

3.  Enter your credentials and click on _Sign In_

    ![](workshops/visualbuilder/media/06.png)

4.  Click on the _hamburger icon_ on the top left, scroll down and click on the _Platform Services_ menu and then on _Visual Builder_

    ![](workshops/visualbuilder/media/07.png)

5.  On this screen, you can manage all your Visual Builder instances. Although Visual Builder handles versioning and different environments (dev-staging-production), you may want to create different and standalone Visual Builder instances. For now, you need one single instance for this workshop. Click the _Create Instance_ button

    ![](workshops/visualbuilder/media/08.png)

6.  In the next screen, set an instance name and a contact email address (you will receive mails on such address when the instance gets created, deleted, etc). Leave all others fields as-is and click _Next_ to continue

    ![](workshops/visualbuilder/media/09.png)

7.  Click _Create_ to submit the request

    ![](workshops/visualbuilder/media/10.png)

8.  The creation will take about 5 minutes. You can click the refresh button to update the status any time

    ![](workshops/visualbuilder/media/11.png)

9.  Once it gets created, you can click the instance's hamburger menu for the next operations. Click _Start_ or _Stop_ to start or stop the instance. Click _Delete_ to delete it (warning: you will lose all your applications if you haven't exported them in advance!!)

    ![](workshops/visualbuilder/media/12.png)

    ![](workshops/visualbuilder/media/13.png)

#### TIP
The just created VBCS instance will start to consume Universal Credits from your free trial budget (400€). We **DO RECOMMEND** you to **STOP** the instance while you're not going to work with it. That way, your free budget will last more days (up to one month)

10.  Click the _Open Visual Builder Home Page_ to get to the VBCS main page. **Tip:** bookmark this URL so that you can open it directly any time without needing to go through the Oracle Cloud Infrastruture console menus.

11.  You're now in the VBCS console. Proceed with the next section!

### Visual Builder Application Structure & Settings



