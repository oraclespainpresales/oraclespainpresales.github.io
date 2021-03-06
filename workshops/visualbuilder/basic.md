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

4.  Enter your personal information in the next form. You can select either Personal or Company use for _Account Type_. Type in your _Cloud Account Name_, which must be unique across all Oracle Cloud. Select your _Home Region_ mainly based on your geographic location. Take into account that trial accounts like this one, will NOT allow you to subscribe to other Oracle Cloud regions (with paid accounts you can subscribe to any region you want, without any additional cost) nor changing it afterwards.

    You may want to review first the Cloud Services available on each one [here](https://www.oracle.com/cloud/data-regions.html) before selecting _Home Region_.

    If you’re located in Europe, we suggest to use Frankfurt, Amsterdam or London.

5.	Enter the password you will use later for Cloud login.

6.	Click on _Review Terms and Conditions and Complete Sign-Up_

7.	Review your email INBOX. You will receive **two separate** mails. Wait until you receive a message with the subject “**Your Oracle Cloud Account is Fully Provisioned**” as follows:

    ![](workshops/visualbuilder/media/04.png)

8.	Click the _Sign In to Oracle Cloud_ button to get logged to Oracle Cloud with the username (email used) and password.

### Setting up your new trial account for the Oracle Visual Builder workshop

Your brand new Oracle Cloud Trial account is ready but you haven't yet created all the services/artifacts needed for the workshop. Follow the next steps to get ready:

1.  If not yet logged in, go to the Oracle Cloud Infrastructure (**OCI**) console URL: `https://console.your_region.oraclecloud.com/` where `your_region` is the home region selected during the trial request in step 4 above. For example:

    | Home Region   | OCI Console URL                                 |
    | ------------- |-------------------------------------------------|
    | Frankfurt     | https://console.eu-frankfurt-1.oraclecloud.com/ |
    | Amsterdam     | https://console.eu-amsterdam-1.oraclecloud.com/ |
    | London        | https://console.uk-london-1.oraclecloud.com/    |

    For other Home regions URLs check [here](https://docs.cloud.oracle.com/en-us/iaas/Content/GSG/Tasks/signingin.htm)

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

    **TIP:** The just created VBCS instance will start to consume Universal Credits from your free trial budget (400€). We **DO RECOMMEND** you to **STOP** the instance while you're not going to work with it. That way, your free budget will last more days (up to one month)

10. Click the _Open Visual Builder Home Page_ to get to the VBCS main page. **Tip:** bookmark this URL so that you can open it directly any time without needing to go through the Oracle Cloud Infrastruture console menus.

### Install additional artifacts

1. Before moving on, you still need to create some additional artifacts (helpers) for the workshop. Open the OCI console (for example [https://console.eu-frankfurt-1.oraclecloud.com](https://console.eu-frankfurt-1.oraclecloud.com)) and remember to login using your **SSO account**

2. Expand the hamburger icon on the top left, scroll down and click on the _Resource Manager_ menu

    ![](workshops/visualbuilder/media/19.png)

3. You're going to create a set of OCI resources (REST service mockups) that will later be used by the VBCS workshop. To make it easier, we provide a `Resource Manager` stack that will provision all those resources automatically using Terraform. In this `Resource Manager` screen, click the _Create Stack_ button

    ![](workshops/visualbuilder/media/20.png)

4. In the next screen, make sure you have selected _MY CONFIGURATION_ option and _.ZIP FILE_ as the TERRAFORM CONFIGURATION SOURCE. Upload [this ZIP file](https://github.com/oraclespainpresales/oraclespainpresales.github.io/raw/master/workshops/visualbuilder/artifacts/apigw.zip) as the _Stack Configuration_ and click _Next_ leaving all other settings as default

    ![](workshops/visualbuilder/media/21.png)

5. Click _Next_ to continue (**do not modify the default content for `TENANCY_OCID` and `REGION` variables**)

    ![](workshops/visualbuilder/media/22.png)

6. In the `Review` screen click _Create_ to create the _Stack_

7. Once created, open the _Terraform Actions_ menu and click _Plan_ to create a new `Plan` job

    ![](workshops/visualbuilder/media/23.png)

8. Let the job run until it succeeds and then click the _Stack Details_ link to go back to the `Stack` screen

    ![](workshops/visualbuilder/media/24.png)

9. Open the _Terraform Actions_ menu again and now click _Apply_ to apply the stack

    ![](workshops/visualbuilder/media/25.png)

10. Let the new job run until it succeeds and then scroll down to the end of the `Logs` window. You should see a `Deployed_Routes` log entry with one `Path`. Copy and paste the URL as that service will be used later in the workshop.

    ![](workshops/visualbuilder/media/26.png)

    ![](workshops/visualbuilder/media/27.png)

    If you're curious, you can open the URL in a browser to see the response.

You can now continue reading the basics of Visual Builder in the next sections, or go straight to start the Hands On Lab!

### Visual Application Structure & Settings

A visual application is a collection of resources that you use to develop web and mobile applications. A visual application includes metadata in JSON files that describe data sources and business objects, and includes the HTML and JavaScript files of the web application.

Once you're logged in Visual Builder console, you can create a new visual application by clicking the _New_ button (top right) or, if no applications have been created yet, click the _+ New Application_ one:

![](workshops/visualbuilder/media/14.png)

You can type any name and its internal ID will be automatically generated as you type. Each visual application must have a unique application ID:

![](workshops/visualbuilder/media/16.png)

After clicking _Finish_ you have your brand new Visual Application ready.

A Visual Application contains the following components:

![](workshops/visualbuilder/media/29.png)

-   **Web Applications**: web applications that can be hosted by Visual Builder or downloaded to be hosted on any web server of your choice
-   **Mobile Applications**: mobile applications, either PWA (Progressive Web Application) or an iOS and Android native
-   **Service Connections**: to consume existing REST endpoints
-   **Business Objects**: a resource, similar to a database table. They have fields that may hold the data for your application and are stored in a database
-   **Global Settings**: settings shared between all web/mobile applications

The **Service Connections**, **Business Objects** (if used) and the Visual Application **Global Settings** are global and shared within the whole Visual Application.

Similarly, a Web/Mobile application is composed by:

-   **Root Pages**: the entry point/page of the application. You may have more than one root pages, but only one is "active"
-   **Flows**: governs how information is transferred between pages. One or more pages form a page flow. Within a flow, you can set up navigation from page to page
-   **Pages**: from a UI perspective, it contains all web components
-   **Javascript**: Javascript code that can be called from pages and other components
-   **CSS**: stylesheets that can be imported to the app
-   **Images**: images that can be imported to the app
-   **i18n**: localization settings to make your app multilingual
-   **Settings**: application-specific settings

#### Visual Application Global Settings

You can configure settings for a visual application that affect the artifacts within it, while other settings are application-specific. You configure settings for a visual application in the Settings editor by clicking the application hamburger icon (top right) and _Settings_ option:

![](workshops/visualbuilder/media/30.png)

The settings for a visual application are grouped into tabs in the Settings editor:

![](workshops/visualbuilder/media/31.png)

-   **Application**: You can configure the value for the Vanity URL property, which is not part of this workshop. See [Specify a Custom App URL](https://docs.oracle.com/en/cloud/paas/app-builder-cloud/visual-builder-developer/specify-custom-url.html#GUID-D7FF0F98-009E-4EF7-87EB-A87D8B60A02D) for more info.
-   **Translations**: Download and upload strings that appear in the user interface of your visual applications, for localization purposes. This topic is handled in the Advanced workshop.
-   **Application Profiles**: An application profile allows you to deploy your app with different settings depending on the target environment. This topic is handled in the Advanced workshop.
-   **Team**: By default, only the application creator user (plus platform administrators) have privileges to see and edit the project. Adding _Team members_ allows you specify additional tenant users to collaborate on the visual application.
-   **User Roles**: You can create custom roles to fine-grained control the to business objects and data in your apps. This topic is handled in the Advanced workshop.
-   **Business Objects**: Controls the security for the BO API access. You can configure anonymous access, basic authentication, or get an access token that a client can use.
-   **Services**: Add or configure connections to a catalog of backend services provided by Oracle, such as Oracle Cloud Applications and Oracle Integration Cloud (OIC) services (Integration and Process). The OIC integration is handled in the Advanced workshop.

### Web/Mobile Application Structure

As noted in previous sections, a Web (or mobile) application is composed by a number of elements: flows and pages, _helpers_ like javascript, CSS, or images and its own set of settings

![](workshops/visualbuilder/media/32.png)

When you create a new application, Visual Builder creates a skeleton for you with a minimal set of elements:

![](workshops/visualbuilder/media/33.png)

`shell`: the default root page. By default, this will be the _entry point_ to the app and the **container** for the rest of the pages
`main`: the default page flow. Each page in your application is contained within a flow. You create a flow to group one or more pages that you might want to treat as an independent unit that performs some function in your application
`main-start`: the default (empty) page, contained in the `shell` root page. You will place your UI components in the _pages_
`app.css`: empty CSS file where you can place your own styles

Of course, you can create additional elements by clicking the **+** button on the right of each type of element

When you click any of the above artifacts, its configuration page tab will be opened on the right.

### Variables, Events, Actions and scope of those

The Web/Mobile application, its flows and its pages, have all a set of artifacts that allow you to build the logic of the application:

-   `Variables and Types`: You use variables to store data that can be used by actions and page components in your application. For each variable you must specify a `Type` property to define the type of data that is stored in the variable. You have the usual scalar types (string, number, etc) and you can also crete your own type structures. A variable can have a default value and can also be defined as a `Constant`

    - You can define a `Type` as a JSON object or as an Array, and then specify its attributes:
    
    ![](workshops/visualbuilder/media/46.png)
    
    - You can also create a type based on an existing REST endpoint, very convinient when you need to map the input or output of a call:

    ![](workshops/visualbuilder/media/47.png)

    - Variables can be of type scalar (_any_, Array, Boolean, Number, Object or String), of an existing `Type` or of a Data Provider. You can also specify it as a regular variable or as a constant:

    ![](workshops/visualbuilder/media/48.png)

    - Once a variables has been created, there are some other attributes than can be set on it, such as defining it as an _Input Parameter_, set a _Default Value_ or set a persisting policy. You can also link an _Action Chain_ to the variable so that whenever it gets updated, the Action Chain flow gets triggered:

    ![](workshops/visualbuilder/media/49.png)

-   `Events`: an Event is a sort-of message that is produced by an artifact and may have zero or many _event listeners_. An _event listener_ will execute some kind of action as the result of the arrival of the subscribed event. There are several types of events in the runtime: page events, flow events, system events, custom or developer-defined system events, component (DOM) events, and variable events

    - You can specify multiple event listeners and link one or more _Action Chains_ to each event:

    ![](workshops/visualbuilder/media/52.png)

    - You can create your own _Custom Events_ and set input parameters if needed:

    ![](workshops/visualbuilder/media/50.png)

    ![](workshops/visualbuilder/media/51.png)

    - _Custom Events_ can be triggered from within the _Action Chains_

    - _Lifecycle Events_ allow users to have the control of the lifecycle of the application, triggering _Action Chains_ when page gets loaded or exited, for example:

    ![](workshops/visualbuilder/media/53.png)

-   `Action Chains`: An action chain is a sequence of actions that you create to define the behavior of components. Action chains are triggered by events that you add to components and page events, etc

    - Building the flow of an _Action Chain_ is extremely easy and 100% visual. There are many activities available, including those for flow logic, navigation and also to integrate with Oracle Integration Process:

    ![](workshops/visualbuilder/media/54.png)

    - Each _Action Chain_ activity has its own set of properties to be configured:

    ![](workshops/visualbuilder/media/55.png)

#### Scope

It is important to understand the scope of the Variables, Events and Action Chains in your Visual Builder applications:

![](workshops/visualbuilder/media/34.png)

As you can see in the above diagram, you can have Variables/Events/Action Chains at _Application_, _Flow_ and _Page_ levels. It is pretty obvious to assume the scope of each of those:

-   Artifacts (Variables/Events/Actions) defined at `MyWebApplication` level, will be available from **everywhere** in the application
-   Artifacts defined at `main-flow` level, will only be accessible from the flow itself and from `page1` and `page2` pages
-   Artifacts defined at `page1` level, will only be accessible from the `page1` itself
-   Variables defined at an `Action Chain` level, will only be accessible from such Action Chain
-   ...and so on and so forth

### Page Designer

When you open a `page` you will get opened the Page Designer, which consists on a **Components Palette**, a **Page Structure** view, a **Page Editor** and, when any UI component is selected, the **Property Inspector** (of such component):

![](workshops/visualbuilder/media/35.png)

In the **Property Inspector** you will be able to set the specific properties of the UI component, register any event (e.g.: click on a _Button_) and set any of the component specific and general HTML attributes:

![](workshops/visualbuilder/media/37.png)

Additionaly the Page Designer includes a toolbar with the following options:

![](workshops/visualbuilder/media/36.png)

Designing your page is as easy as dragging and dropping the UI components from the **Component Palette** to the Page Editor's canvas. We will do so during the Hands On Lab later

### Web/Mobile Application Specific Settings

Besides the Visual Application general settings, that will affect all the contained Web & Mobile applications, each application has its own settings, only applicable to it. To open such settings tab, simply make sure you have selected the web/mobile application and click on the _gear_ icon:

![](workshops/visualbuilder/media/38.png)

You can mainly set the following parameters (among others):

-   **Default Page**: Should you have multiple Root Pages in your application, select which is the default one
-   **Theme**: Should you have a complete CSS file, you can set the app to use such CSS as default
-   **Allow anonymous access**: By default this setting us unchecked. That means the application will need authentication to open it. Should you want the app to be anonymous (available to everyone without auth), just check this option
-   **Embedding**: A Visual Application is a regular HTML5 web app. As such, it could be embedded in an external application through the `<iframe>` or `embed` tags. If you plan to do so, you must first allow it at Visual Builder level

### Application Testing

You have two options to test your Web application:

![](workshops/visualbuilder/media/39.png)

1.  While you have your page opened in the Page Editor canvas, click the `Live` button from the toolbar (top-right). You'll notice the canvas will be now surronded by a green rectangle. That means the canvas is now in _Live Mode_, and you can interact with the UI components as if the application were deployed. This option is very convenient for quick tests in your page.
    You also have a keyboard shortcut to temporary enable the _Live Mode_: hold the CTRL key (or CMD on Mac)
2.  Click the _Play_ button on the Visual Application toolbar (top-right). The whole application will be opened in preview mode in a new tab in your browser. You can notice that the app URL includes the version number and the mode (preview)

### Application Lifecycle

A Visual Application can be easily versioned from the application browser. You'll get to the application browser when you login to Visual Builder or, if you have an application already opened, by clicking the top-left hamburger icon and then click All Applications to close the current one and open the application browser:

![](workshops/visualbuilder/media/40.png)

![](workshops/visualbuilder/media/41.png)

Each **application** may have one or multiple versions and **each version** may have four status:

-   **Development**: In the development stage you design your application by building pages and creating business objects. You also use development versions to update the application to fix any problems revealed while testing the application.
-   **Staging**: You use the staged application to prepare the application for publication. You can distribute the URI of the staged application to team members who can help you test the behavior of the application, identify where it can be improved and to test your changes. You can re-stage a version as many times as you need.
-   **Live**: Each time that you are ready to publish a new version of your application you should lock the live version of your application until the new version is published. You cannot make changes to a version of an application after it is published and live. To make additional changes to the application you need to create a new version. The URL of a Live application **does not change from version to version**.
-   **Obsolete**: Indicates that this version was published but has been superseded by a newer version. Obsolete applications are read-only 

You can change the stage (**Development** --> **Staging** and **Staging** --> **Live**) from within the application right-hamburger icon in the Application Explorer...

![](workshops/visualbuilder/media/42.png)

or through the opened application top-right hamburger icon

![](workshops/visualbuilder/media/43.png)

To create a new version of an existing application, simply use the _New Version_ option in the hamburger menu of the application while in **Application Explorer**. You can set any version number as long as doesn't already exist.

![](workshops/visualbuilder/media/44.png)

You can have as many versions as you want in **Development** and **Staging** stages. However you can only have _one_ **Live** version at a time.

![](workshops/visualbuilder/media/45.png)

```
Note: the Mobile Applications lifecycle is similar to the web ones.
However, it adds a way to deploy the app in your mobile device during Staging and Live.
Mobile applications are not handled in this Basic workshop.
```

### Business Objects

A business object is a resource similar to a database table; it has fields that hold the data for your application. Like a database table, a business object provides the structure for data. Business objects are stored in a database. The apps in your visual application and other clients access the business objects via their REST endpoints.

The Business Objects pane in the Navigator lists all the business objects that are available for use in your application:

![](workshops/visualbuilder/media/56.png)

When you create a new Business Object, you're actually creating a regular database table. As such, it will contain _columns_ (a.k.a. _fields_). There are some Fields pre-created by Visual Builder, and you can add your own:

![](workshops/visualbuilder/media/57.png)

![](workshops/visualbuilder/media/58.png)

Each field has its own set of properties, than can be set based on your needs:

![](workshops/visualbuilder/media/59.png)

You can setup fine-grained security access to each Business Object in the _Security_ section. Here, you can, for example, enable the access to the data from _Anonymous applications_, specify content-based rules on the CRUD methods, etc:

![](workshops/visualbuilder/media/60.png)

Whenever a Business Object is created, a set of RESTful APIs are made available for perform CRUD operations on it. The APIs URLs and methods are provided on this screen:

![](workshops/visualbuilder/media/61.png)

Finally, you can access the Business Object contents to manually create, edit or remove rows on it. You can also export and import data in CSV format:

![](workshops/visualbuilder/media/62.png)

### Hands On Lab - Step 0: Use Case Description

You're a developer in ACME, a leading company, and the business users have requested a web application to review the deals during the year 2019. The data is currently contained in a CSV file ([download](https://github.com/oraclespainpresales/oraclespainpresales.github.io/raw/master/workshops/visualbuilder/artifacts/deals.csv)). They want to see all deals in a table-like list, with information about the sales representative of each deal and also its status. Posibility to filter the deals based on such status is also a requirement.

You soon realize that Oracle Visual Builder perfectly fits on these requirements to build such web application.

### Hands On Lab - Step 1: Create the Visual Application 

Login to your VBCS instance and click the `+ New Application` button, should you don't have any app created yet, or the `New` button on the top right otherwise:

![](workshops/visualbuilder/media/63.png)

![](workshops/visualbuilder/media/64.png)

Enter _Deal Reviewer_ as the `Application Name` and click `Finish`:

![](workshops/visualbuilder/media/65.png)

### Hands On Lab - Step 2: Business Object creation & Data import

On the left palette, click the `Business Objects` icon:

![](workshops/visualbuilder/media/66.png)

We're going to create the `DEALS` Business Object directly from the provided CSV file. Click the hamburger icon and click the `Data Manager` link:

![](workshops/visualbuilder/media/67.png)

In the Data Manager menu, click the `Import Business Objects` option and import the `deals.csv` file:

![](workshops/visualbuilder/media/68.png)

![](workshops/visualbuilder/media/69.png)

Click `Next` twice and then `Finish`, leaving all options as default:

![](workshops/visualbuilder/media/70.png)

![](workshops/visualbuilder/media/71.png)

Once finished, click `Close`:

![](workshops/visualbuilder/media/72.png)

Click on the just created _Deals_ Business Object on the left to review it:

![](workshops/visualbuilder/media/73.png)

Check the `Fields` and the `Data`

### Hands On Lab - Step 3: Service Connections Definition

Business Users have requested to be able to filter the deals based on the _Deal status_. To do so we need to know what the possible status options are. For that purpose, we have been given a RESTful external service that will return those.

Such RESTful external service is actually the _artifact_ deployed at the beginning of the Lab through the OCI Resource Manager feature. In order for VBCS applications to invoke external service, we must first register those. All registered services will be available to all web & mobile applications in the VBCS project.

Click the _Service Connections_ icon on the left menu and then click the _+ Service Connection_ button:

![](workshops/visualbuilder/media/74.png)

Select the _Define by Endpoint_ source:

![](workshops/visualbuilder/media/75.png)

In the next screen paste the URL you previously copied when creating the _Resource Manager_ artifact and click _Next_:

![](workshops/visualbuilder/media/76.png)

The next wizard step shows all the service details. To complete the setup, we must first let VBCS know the JSON payload that will be returned by the service. Click the _Test_ tab, click the _Send_ button to send a request to the service, and once completed you will see the returned JSON body. Click the _Save as Example Response_ and _Create_ to finish the service creation:

![](workshops/visualbuilder/media/77.png)

You are now ready to start building the Web Application!

### Hands On Lab - Step 4: Create the Web Application

On the left menu, click the _Web Applications_ button and then click _+ Web Application_:

![](workshops/visualbuilder/media/78.png)

Type `DealsReviewerApp` as the _Application Name_, leave the _Navigation Style_ as `None` and click _Create_:

![](workshops/visualbuilder/media/79.png)

Review the artifacts created by VBCS: one `main` flow with a `main-start` web page. All embeded by the `shell` root page:

![](workshops/visualbuilder/media/80.png)

`Hint: you can hide/show the sections by clicking the section button when selected to make more room for other sections on the screen:`

![](workshops/visualbuilder/media/81.png)

### Hands On Lab - Step 5: Build Visual Structure

To build our web application, we have drawn on the following mockup:

![](workshops/visualbuilder/media/139.png)

The main page will contain a list of the deals, where each row will show information about the Deal's sales rep, amount, status and date. Also, it'd be nice to show an avatar picture of the sales rep on the left. On top of the list, a dropdown ui component will allow us to filter the list based on the deal status.

Additionally, when selecting any of the deals, the list will be shrinked to the 50% of the screen to make room for a new panel on the right:

![](workshops/visualbuilder/media/140.png)

which will display some more details about the selected deal's Sales Rep like two charts about his/her achievement.

Once we create a new Web App not based on any template, we start with a completely empty page. So let's start first dragging & dropping all containers.

Locate the _Panel_ component in the _Components_ palette and drag & drop it in the emptied structure view:

![](workshops/visualbuilder/media/141.png)

![](workshops/visualbuilder/media/142.png)

By default, VBCS uses the _Grid Row_ container, a 12-column grid that is useful when you want to align components precisely according to the grid. But for our purpose, we need to change it to a _Flex Container_ (the flex container is a flexible container which is useful for responsive designs that optimize the use of the available space):

![](workshops/visualbuilder/media/143.png)

Select the top _Grid Row_ and on its properties, change it to _Flex_:

![](workshops/visualbuilder/media/144.png)

Do the same with the other _Grid Row_ under the _Panel_ element, setting its direction to `Vertical`:

![](workshops/visualbuilder/media/145.png)

Inside the Top _Flex Row_ drag & drop an additional _Panel_ and, once done, make sure to change the contained _Grid Row_ to _Flex_ as with the previous ones:

![](workshops/visualbuilder/media/146.png)

![](workshops/visualbuilder/media/147.png)

On the First Panel, set the _Item Sizing_ to `Auto`:

![](workshops/visualbuilder/media/154.png)

On the last _Flew Row_, change also the _Direction_ to `Vertical`, the _Align_ to `center` and _Wrap Items_ to `Don't Wrap`:

![](workshops/visualbuilder/media/148.png)

Also, in order to make sure all containers expand to the right size, add the following CSS _style_ attributes:

Top Flex Row: `height:82vh`
First Panel: `max-height:82vh`
First Panel's Flex Row: `height:100%`
Second Panel: `height:82vh;min-width:40vw;max-width:60vw`
Second Panel's Flew Row: `width:100%;height:100%`

You can set the CSS _style_ attribute by selecting the component and clicking the _All_ properties tab and within the _General Attributes_ section:

![](workshops/visualbuilder/media/149.png)

The _Second Panel_ must only be displayed under certain circumstances (that will be handled later). You can add conditions to display any UI component in VBCS by surrounding it with with an `if` clause.

To do so, right-click on the _Second Panel_ and select `If` under the _Surround_ menu:

![](workshops/visualbuilder/media/150.png)

We will set the condition later and, for now, we don't want this panel to be displayed. So, select the `Bind If` element and clicking the _fx_ button, set the default condition from `true` to `false`:

![](workshops/visualbuilder/media/151.png)

### Hands On Lab - Step 6: Add List Component and retrieve BO data

To display the deal information, we're going to use a `List` component.

First, let's add a new _Flex Container_ inside the First Panel's _Flex Row_ seeting its _Direction_ to `Vertical` and adding the _style_ `height:90%` to it:

![](workshops/visualbuilder/media/152.png)

![](workshops/visualbuilder/media/153.png)

In the `Components` tab, scroll down until the `Collection` section and drag & drop the `List View` component into the just added _Flex Container_:

![](workshops/visualbuilder/media/82.png)

![](workshops/visualbuilder/media/83.png)

Once added, you can view (and edit!) the HTML source code of the page by clicking the `Code` button:

![](workshops/visualbuilder/media/85.png)

Click the `Design` button to go back to the WYSIWYG view. Expand (if needed) the `Properties` section and click the `List View` component in the Structure section to display the List component properties:

![](workshops/visualbuilder/media/86.png)

When just dropped, the List View component displays some dummy data just to show you how it will be rendered. However, no data is yet linked to the component. We will get that using the DEALS Business Object created in the previous sections. You will see how easy is to set a _data source_ to a component in VBCS.

With the `List View` component selected, click the _Quick Start_ property tab. For certain components, such as Tables, List Views, Dropdown and others, VBCS provides a set of wizards to specify the component data source and easily create CRUD pages. Click the _Add Data_ option to set our `List View` component's data source:

![](workshops/visualbuilder/media/87.png)

In the opened wizard, we can select any of the **already registered** available data sources, either a Business Object or an external service. Select the `Deals` Business Object and click _Next_:

![](workshops/visualbuilder/media/88.png)

From the two available templates, select the one on the left and click _Next_:

![](workshops/visualbuilder/media/89.png)

You can now bind the different payload attributes from the RESTful call response, to specific template spots by dragging & dropping the field onto the spot. Do it as follows:

1.  (leave it empty)
2.  `repName` and `repSurname`
3.  `dealAmount`
4.  `customer`
5.  `dealDate` (set its type as _Input Date_)

Also, drag & drop the field `status` in the _Include in row data_ box on the right. Then click _Next_:

![](workshops/visualbuilder/media/90.png)

On the last step of the wizard you can set a generic filter, sorting and other parameters in the Data Source, but we'll leave this as-is. Just click _Finish_:

![](workshops/visualbuilder/media/91.png)

You now can see how after setting the List View's data source, the data is refreshed in real-time even in the design page, based on the bindings you have just specified in the wizard:

![](workshops/visualbuilder/media/92.png)

### Hands On Lab - Step 7: Test what you have done so far

Although you see the life data during design time, let's bring the Preview feature of VBCS.

Whenever you want during the development of an application, as explained before in the _Application Testing and Lifecycle_ section, you can click the _Live_ button from the toolbar or click the _Play_ button on the Visual Application toolbar (top-right).

![](workshops/visualbuilder/media/39.png)

Do so and review what you have done so far.

### Hands On Lab - Step 8: Include Avatar picture in table

It'd be nice to add an actual picture of the sales rep of each deal entry on the table. We can do so very easily following the next steps.

First, download this [file](https://github.com/oraclespainpresales/oraclespainpresales.github.io/raw/master/workshops/visualbuilder/artifacts/avatars.zip) to your desktop. Then, in the Application Structure view, open the _Resources_ folder and right-click in the _images_ subfolder to finally click the _Import_ menu:

![](workshops/visualbuilder/media/93.png)

Select or drag & drop the previously downloaded `avatars.zip` file and click _Import_. VBCS will unzip the contents automatically:

![](workshops/visualbuilder/media/94.png)

You can see all images imported if you expand the _images_ folder:

![](workshops/visualbuilder/media/95.png)

With all avatars already imported in the app, let's add the avatar image in the existing List View component.

To do so, simply locate the _Avatar_ component in the palette, and drag & drop it on top of the `List View` component either in the Structure view or in the canvas.

**IMPORTANT**: make sure you drop the component in the _image slot_. First drag the _Avatar_ component over the `List item` until the slots popup appears; then, without yet dropping it, move the _Avatar_ component to the _image_ slot:

![](workshops/visualbuilder/media/96.png)

However, you still see a black square. Let's bind the _data_ (source) of the new avatar component to the right picture.

If you reviewed the uploaded images, you probably have noticed each image filename corresponds to a `NameSurname.jpg` pattern. No need to say that the concatenation of the `repName` and `repSurname` fields plus `.jpg` will make the trick!

So, select the avatar component in the Structure view (or select the black square in the canvas) to open its properties section. Go to the _Data_ tab and click the _Src_ field's Expression Editor (`fx` button):

![](workshops/visualbuilder/media/97.png)

type the following value:

`$application.path + 'resources/images/' + $current.data.repName + $current.data.repSurname + '.jpg'`

![](workshops/visualbuilder/media/98.png)

Finally, go to the _General_ tab and set the _Size_ to `Extra Small`:

![](workshops/visualbuilder/media/99.png)

Now, the list looks much better!

![](workshops/visualbuilder/media/100.png)

### Hands On Lab - Step 9: Improve data visualization with templates and your own CSS styles

You can see how the _deal amount_ number is not properly formatted as currency. We're going to change the existing format of the deal amount with an _Input Number_ component.

Drag & drop an _Input Number_ component from the palette **inside** the `<> div@value1` element in the Structure View:

![](workshops/visualbuilder/media/107.png)

You can now remove the previous `Bind Text` component by right-clicking on it and clicking on _Delete_:

![](workshops/visualbuilder/media/108.png)

And now let's set the data binding and format for the new component. Click on the _Input Number_ element and in the _Data_ tab of its properties click on the _fx_ icon of the _Value_ field:

![](workshops/visualbuilder/media/109.png)

In the Expression Editor, drag & drop the `dealAmount` variable to the edit window and click _Save_ when done:

![](workshops/visualbuilder/media/110.png)

In the _General_ tab, set the following settings:

-   _Readonly_: `checked`
-   _Converter_: `$`
-   _Currency Format_: `Short`
-   _Maximum Fraction Digits_: `0`

Now the deal amount will be displayed in a better way:

![](workshops/visualbuilder/media/111.png)

Let's going to provide a better format to the deal date, too. Click on the _Input Date_ element either in the Structure View or in the canvas:

![](workshops/visualbuilder/media/112.png)

In the _General_ tab, set the following settings:

-   _Converter_: `Pattern`
-   _Pattern_: `dd-MMM-yyyy`

![](workshops/visualbuilder/media/113.png)

Finally, to demonstrate how we can use our own CSS styles in VBCS, let's highlight the deal's _Company name_ (`customer` field) using an own CSS class.

First, open the `app.css` file under the `Resources/css` folder:

![](workshops/visualbuilder/media/101.png)

The file should be empty. Type in the following code:

```
.company {
  color: red;
  font-size: 20px;
}
```

that defines the CSS class `company` with specific font size and color.

![](workshops/visualbuilder/media/102.png)

Now, let's make use of the new class. In the _Structure View_, select the `<> div@title2` component in the hierarchy tree:

![](workshops/visualbuilder/media/103.png)

and type `company` in the _Class_ field in the properties panel:

![](workshops/visualbuilder/media/104.png)

You will immediately see how the Company name is highlighted in red with a bigger font size, as the `company` class dictates:

![](workshops/visualbuilder/media/105.png)

Should the Company name does not get updated in the canvas, click the _Reload page_ button on the top bar:

![](workshops/visualbuilder/media/127.png)

If you are not yet a believer, open the source code of the page and see what you're really doing:

![](workshops/visualbuilder/media/106.png)

This is pure HTML5+CSS stuff in a LowCode way!

### Hands On Lab - Step 10: Add filter from external service

If you remember, the business users would like to filter the list based on the status of the opportunity.

First, we're not yet displaying the opportunity status in the list, so let's do so.

Drag & drop a _Text_ component **inside** the `<> div@value1` element:

![](workshops/visualbuilder/media/114.png)

You will see that the _Text_ component has been placed just below the deal amount field but not yet bind to any data source (its default content is `Bind Text`):

![](workshops/visualbuilder/media/115.png)

Click the new element either in the Structure View or in the canvas and, in the Properties View, click the _fx_ button of the _Value_ field. As done before, drag & drop the `status` field (don't forget to clear the existing `Bind Text` value before the drag & drop).

We can see now each opportunity status as part of the data displayed in the List View:

![](workshops/visualbuilder/media/116.png)

Time to provide the requested filter feature. We can use the typical HTML Dropdown component to select which deal status we're filtering by, and then apply such filter on the data. The HTML Dropdown component is available in VBCS as _Select (Single)_ UI component.

Let's first add the _Select (Single)_ component to our design. Drag & drop it inside the _Flex Container_ containing the _List View_ and and just above the it:

![](workshops/visualbuilder/media/117.png)

![](workshops/visualbuilder/media/120.png)

if you get to place it in the wrong spot, you can always _Undo_ the operation or simply delete it and try again.

Now select the new _Single Select_ element, change the _Label Hint_ to `Filter by Opportunity Status`.

Go to the _Quick Start_ tab to set the element's Data Source. Click the _Add Options_ option and select the only endpoint available as a Service Connection as follows, and then click _Next_:

![](workshops/visualbuilder/media/121.png)

In the next wizard screen, drag & drop the `code` attribute to the `Value` box, and the `name` attribute to the `Label` box and click _Next_:

![](workshops/visualbuilder/media/122.png)

Click _Finish_ to end with the wizard. You can test what you've just done if you change to _Live_ mode (or hold the CTRL / CMD key) and simply expand the dropdown.

We have successfully fed the dropdown component with an external service, but we still need to store the selected value somewhere.

Go to the element's _Data_ tab. After setting the binding with the wizard, some values have been automatically set. But you can see the _Value_ field is empty. In here is where we will bind a variable to hold the selected value of the dropdown component.

There's no variable yet for that, but VBCS allows us to create one from the menu. Just click the ▼ icon in the _Value_ field and click the _Create Variable_ link (whether to create the variable in the Page, Flow or Application scope, it depends on you and where you will be using such variable somewhere else in the application; in this case, we recommend to create a Page variable):

![](workshops/visualbuilder/media/123.png)

Just name it `filter`, for example, of type _String_.

Now, we still need to apply the filter to the data retrieved from the Business Object.

Go to the page's _Variables_ tab and click the `dealsListSDP` variable.

_This variable, is of type Service Data Provided. It was automatically created when we run the List View Quick Start wizard and handles the requests to the Business Object to gather the data_

In the Property View, there are a number of optional input parameters that can be set to control the number of records returned, apply queries or filters, etc. In our case, we're going to set a filter criteria based on the `filter` variable.

Click on the _Assign_ link for _Parameters_:

![](workshops/visualbuilder/media/124.png)

Click on the `filterCriterion` parameter. We will use the editor _Builder_ to specify the condition. Click on _Click to add condition_:

![](workshops/visualbuilder/media/125.png)

For the _Attribute_ scroll down and select the `status` field. For the _Value_ select `$variables.filter`. And for the operation, better select `equals ($eq)`, and click _Save_:

![](workshops/visualbuilder/media/126.png)

You're done!!

You can now test your web app by clicking the _Play_ button and try your new filter capability.

### Hands On Lab - Step 11: Publish your app

As explained in the _Application Lifecycle_ section above, a VBCS project and all the web or mobile applications contained on it, can have four status: _Development_, _Staging_, _Live_ and _Obsolete_.

Moving an application from _Development_ to _Staging_ means we're in a _test_ stage of the application. We can still develop on such version.

Moving an application from _Staging_ to _Live_ means we're rolling out this version of the application as the new production version for it. _Live_ versions are read-only and cannot be modified. Should you want to make new changes, you'll need to create a new version. _Live_ web applications have the same URL.

You cannot rollback from _Staging_ to _Development_ or from _Live_ to _Staging_

When you have Business Objects in your project, you'll be asked about what to do with the BO data contained in the application, taking into account that the Data (not the BO metadata or definition, but the data itself) is related to the application lifecycle status.

When moving from _Development_ to _Staging_:

![](workshops/visualbuilder/media/128.png)

When moving from _Staging_ to _Live_:

![](workshops/visualbuilder/media/138.png)

In our case, we will be _moving_ the data from _Development_ (which is where we imported the BO definition and data) up to _Live_. So select "Populate Stage with Development data" when Staging the application first:

![](workshops/visualbuilder/media/129.png)

Once _Staged_, you can check the new status in the top bar:

![](workshops/visualbuilder/media/130.png)

Or if you _close_ the editor by clicking the top-left hamburger icon and then _All Applications_:

![](workshops/visualbuilder/media/131.png)

you can see the status of all your projects & versions in your VBCS instance:

![](workshops/visualbuilder/media/132.png)

Finally, let's move from _Stage_ to _Live_. Only _Staged_ projects can be promoted to _Live_. You can promote a project from within the Applications list menu by clicking its hamburger icon:

![](workshops/visualbuilder/media/133.png)

or, if you have your project opened, by clicking the top-right hamburger icon menu:

![](workshops/visualbuilder/media/134.png)

Either so, click the _Publish_ option making sure you select the option "Include data from Stage":

![](workshops/visualbuilder/media/135.png)

To obtain the _Live_ URL of your applications, you can click the _Open Published Application_ option in the top-right hamburger icon if you have the project opened in the editor:

![](workshops/visualbuilder/media/136.png)

or in the Applications browser, click the project's _Live_ status link to get a popup menu of all the web & mobile applications contained in such project (remember that you can have multiple web and mobile applications in a single _project_):

![](workshops/visualbuilder/media/137.png)

In either case, a new tab will be opened with the _Live_ URL, that you can bookmark. This _Live_ URL **will never change** when you promote to _Live_ new versions of your project.

For this project, the URL should be similar to this one:

```
https://<your VBCS instance name>-<your tenant name>.builder.ocp.oraclecloud.com/ic/builder/rt/<your VBCS project name>/live/webApps/<your web app>/
```

### Hands On Lab - Step 12: Create a New Version

Although we have published our app already, you will realize we're still missing to include the _Sales Rep details_ as requested and described before:

![](workshops/visualbuilder/media/140.png)

Going back to the VBCS applications browser, our app (version 1.0) is already in _Live_ state and cannot be modified any more. As we still need to add some more development on the application, we need to create a **new version** and continue from it.

Still in the applications browser, click the application's hamburger menu (on the right) and click the _New Version_ option:

![](workshops/visualbuilder/media/155.png)

Type `1.0.1` as the new version and click _Create_:

![](workshops/visualbuilder/media/156.png)

Once created, you can expand the application menu to see all the different versions available and the status of each one:

![](workshops/visualbuilder/media/157.png)

To continue the development, simply click the application name's link of the correspondent _Development_ version. Once opened, notice the new version and status:

![](workshops/visualbuilder/media/158.png)

### Hands On Lab - Step 13: Handle List Selection

This new development is about selecting one of the rows and display a new section with information about the row's ooportunity's sales rep.

So first, we need to capture the event of the selection of a row by clicking on it, and, obviously, getting the selected opportunity's sales rep associated.

In the Structure View, select the _List View_ component. On its Properties View, click the _Events_ tab. Nearly each UI component you can use in VBCS can produce a number of events that you can easily _capture_ and invoke your own procedure when the event gets triggered. Of course, based on the nature of the UI component, the events produced will vary (e.g.: a Button UI component can produce a _click button_ event). Click the _New Event_ dropdown button and select the quick start option _first-selected-item_. This specific event gets triggered whenever you select/click on a new row in the list:

![](workshops/visualbuilder/media/159.png)

VBCS automatically creates the _event listener_ and associates a brand new _Action Chain_ to it, which is opened for you. Before modeling the new Action Chain, let's review what has just been created by the quick start wizard. In the top bar, go to the _Event Listeners_ tab and check how a new Component Event Listener has been created for the List View component and its _first-selected-item_ specific event. Also, it's been associated with a new Action Chain:

![](workshops/visualbuilder/media/160.png)

You can click in the _Go to Action Chain_ link to go back to the Action Chain tab. In here, we will model the flow of the different actions to be performed whenever you select a new row in the List View component. Firstly, we want to keep the Sales Rep data associated with the selected row. As we're goign to reuse such information later when building the details panel, let's keep such information in a separate variable.

Click the _Types_ tab and the _Type_ / _Custom_ button to create a new specific object type:

![](workshops/visualbuilder/media/161.png)

Name it `salesRepType` of type _Object_ and click _Create_:

![](workshops/visualbuilder/media/162.png)

Using the _Add Field_ link, add two fields of type _String_ with names `name` and `surname`:

![](workshops/visualbuilder/media/163.png)

Now let's create a variable of type `salesRepType`. Go to the _Variables_ tab, click the _+ Variable_ button. Type `selectedSalesRep` as the variable name (ID) and scroll down in the _Type_ list until you find the `salesRepType` type to select it. Click _Create_ when done:

![](workshops/visualbuilder/media/164.png)

Let's go back to the Action Chain modeling. Go to the _Actions_ tab and open the `ListViewFirstSelectedItemChangeChain` chain, if not already opened:

![](workshops/visualbuilder/media/165.png)

In this triggered event, two objects are passed as input data containing a JSON object with all the data and a index key of the selected row. We need to extract & copy the name and surname attributes in our brand new variable.

To do so, we first drag & drop a _Assign Variables_ action at the beginning of the flow as follows:

![](workshops/visualbuilder/media/166.png)

Once placed, click on it to open its properties. Click the _Assign_ link to start assigning values to variables:

![](workshops/visualbuilder/media/167.png)

In the mapper, expand the `selectedSalesRep` variable and drag & drop the `rowData` variable on the left to **both** `name` and `surname` attributes:

![](workshops/visualbuilder/media/168.png)

`rowData` is actually the whole row data JSON object, containing the actual attributes we really need: `repName` and `repSurname`.

Click on the mapped `name` attribute and add `.repName` to the formula:

![](workshops/visualbuilder/media/169.png)

Do the same with the `surname` attribute adding `.repSurname` to the formula. Click _Save_ to continue.

Next, we need to load **all** data related to the given Sales Rep. Such data is in the Business Object that already populates the List View, but we need to filter the request by the selected Sales Rep (by its `name` and `surname`). Thus, we need to invoke the existing Business Object REST API but providing a query filter.

Drag & drop the _Call REST Endpoint_ action just after the _Assign Variables_ action in your flow and click the _Select_ link on its Properties View to select which REST service is to be invoked: 

![](workshops/visualbuilder/media/170.png)

Under _Business Objects / Deals_ select the `[GET] /Deals` operation and click _Select_:

![](workshops/visualbuilder/media/171.png)

If we leave this call as-is, all BO data will be retrieved and we don't want that. In the Properties View, click the _Assign_ link in the _Input Parameters_ section:

![](workshops/visualbuilder/media/172.png)

One of the input parameters available is the `q` parameter which makes use of schemes like mongoDB query, SCIM or open search. Click the `q` parameter, **first** make sure the _Expression_ format is selected and then type in the following:

`"repName='" + $page.variables.selectedSalesRep.name + "' and repSurname='" + $page.variables.selectedSalesRep.surname + "'"`

![](workshops/visualbuilder/media/173.png)

Once invoked with this query, we have all data related to the selected Sales Rep, ready to be processed for the charts.

But before doing that, let's show the Sales Rep details panel on the right. Click in the _Page Designer_ tab, click on the _Bind If_ element in the Structure View and click the _fx_ button in the _Test_ field:

![](workshops/visualbuilder/media/174.png)

The _Bind If_ element renders all its underlying HTML elements if the _Test_ formula evaluates to `true`. Our _Bind If_ element wraps the Sales Rep details _Panel_. We want to show it only when a Sales Rep has been selected. As we map the `selectedSalesRep` variable when we select the row in the _List View_, the easiest way to drag and drop the, i.e., `selectedSalesRep.name` attribute, which will evaluates to `true` whenever it has a value:

![](workshops/visualbuilder/media/175.png)

Click _Save_ and then go to _Live_ mode in the editor. Then, select any of the rows and see how the (empty) Panel is displayed:

![](workshops/visualbuilder/media/176.png)

Go back to _Design_ mode. Let's fill up the details panel with information about the Sales Rep.

### Hands On Lab - Step 14: Add Sales Rep details

Let's start by setting the panel's _Flew Row_ style attribute with:

`width:100%;height:100%`

Drag & drop **two** new _Flex Containers_ inside the _Flew Row_:

![](workshops/visualbuilder/media/177.png)

and set the following settings on each one:

First Flex Container:
-   _Direction_: `Horizontal`
-   _Align_: `center``
-   _Add Items Padding_: `checked`
-   _Style attribute_: `width:100%;height:10em`

Second Flex Container:
-   _Style attribute_: `width:100%;overflow-y: auto;`

In the First (top) Flex Container, drag & drop, on this order, the following elements: _Avatar_, _Flex Container_ and a _Button_. In this new _Flex Container_ drag & drop inside a _Heading_ element (a `<> Cell` element is added automatically when dragging certain UI components):

![](workshops/visualbuilder/media/178.png)

![](workshops/visualbuilder/media/179.png)

Select the _Avatar_ element, click the _fx_ button in the _Src_ field and type the following:

`$application.path + 'resources/images/' + $variables.selectedSalesRep.name + $variables.selectedSalesRep.surname + '.jpg'`

As we did before in the List View, we're selecting the sales rep picture by using, in this case, the `selectedSalesRep` variable attributes. Change the _Avatar_ _Size_ to `Extra Large`.

Select the _Flex Container_ that contains the _Heading_ element and set the following properties:

-   _Direction_: `Horizontal`
-   _Justify_: `center`

Selec the _Heading_ element, click the _fx_ button in the _Text_ field and type the following:

`$variables.selectedSalesRep.name + " " + $variables.selectedSalesRep.surname`

Select the _Button_ element and set the following settings:

-   _Display_: `Icons`
-   _Chroming_: `Borderless``
-   _Align_: `flex-start`

![](workshops/visualbuilder/media/180.png)

We're going to use an icon rather than a text for the button. In the _startIcon_ slot, click the _+_ button and select _Icon_:

![](workshops/visualbuilder/media/181.png)

Click the new _Icon_ link and then the _Icon_ button:

![](workshops/visualbuilder/media/182.png)

Scroll down and select the _Delete_ image. Click _Select_ to select it and continue:

![](workshops/visualbuilder/media/183.png)

We still need to add an action to this button. In the Structure View, select the button and in the _Events_ tab in the Properties View, click the _+ New Event_ button and click the _Quick Start: 'ojAction'_ menu:

![](workshops/visualbuilder/media/184.png)

A new Action Chain has been automatically created and associated with the button's _Click_ event. This button will simply close the Sales Rep panel. To do so, we just need to _reset_ the `selectedSalesRep` to empty it.

Drag & drop a _Reset Variables_ action and in the _Variables to Reset_ just scroll down until you find the `selectedSalesRep`:

![](workshops/visualbuilder/media/185.png)

You can try it by going to _Live_ mode, click on any of the rows to display the Sales Rep panel and then the `X` button to close it.

### Hands On Lab - Step 15: Add Charts

During the Step 13 section above, we already got all selected Sales Rep data needed to perform some aggregation operations and prepare the data to be used by the two charts (pie and bar) we want to use.

VBCS charts use a specific JSON type to build them. Let's create a similar type and variables that will be used later to feed the charts.

Go to the _Types_ tab and create a new Custom one by clicking the _+ Type_ button and _Custom_ submenu. Name the new type as `chartType` and add the following fields:

`group` (string)
`id` (number)
`series` (string)
`value` (number)

![](workshops/visualbuilder/media/186.png)

We're going to feed these two charts with a variable of type _Array Data Provider_ (ADP). Go to the _Variables_ tab and create two new variables of type _Array Data Provider_. Name them as `pieADP` and `barADP`. When created, make sure its _Data_ setting is set to _Assign Data Later_, the _Item Type_ is set to the `chartType` type and the _Key Attributes_ is set to `id`:

![](workshops/visualbuilder/media/187.png)

Now, go to the _Actions_ tab and open the `ListViewFirstSelectedItemChangeChain` Action Chain. If there's other Action Chain already opened, you can do so by either selecting it from the dropdown menu or by clicking the _Action Chains_ link to open the Action Chains browser:

![](workshops/visualbuilder/media/188.png)

As done in the previous step, we are retrieving the sales rep data in the _Call REST Endpoint_ action. Now, in the `success` branch, we need to process the data and feed the just created ADP variables.

Drag & drop a _Reset Variables_ and a _Run in Parallel_ actions (on this order):

![](workshops/visualbuilder/media/189.png)

In the _Reset Variables_ action, set both variables `pieADP` and `barADP`. This is to make sure we reset the content of the charts when we change the sales rep selected.

![](workshops/visualbuilder/media/190.png)

We need to use some Javascript code to process the data and produce the needed aggregated JSON array structure that the charts do use. We need to produce two different structures (one for the `pieADP` and the other for the `barADP` variables) and we can do that in parallel, that's why we are using the _Run in Parallel_ action.

Drag & drop a _Call Module Function_ and an _Assign Variables_ actions to two separate branches in the _Run in Parallel_ as follows:

![](workshops/visualbuilder/media/191.png)

Select the first _Call Module Function_. Set the `ID` to `aggregateDealType` and the Label to `Aggregate Deal Type`. Click the _Create_ link to create a new Javascript function named `aggregateDealType`:

![](workshops/visualbuilder/media/192.png)

Select the **second** _Call Module Function_. Set the `ID` to `aggregateDealAmount` and the Label to `Aggregate Deal Amount`. Click the _Create_ link to create a new Javascript function named `aggregateDealType`.

In **both** _Call Module Function_ activities, click the _Assign_ link in the _Input Parameters_ field and drag & drop the `callRestEndpoint1`'s `body` attribute to the `arg1` parameter:

![](workshops/visualbuilder/media/193.png)

Let's write some code!

Go to the _JavaScript_ tab. You see how both functions have been declared but not yet with a body. What we need to do is to perform some aggregation to the input data, which is no more than the JSON response returned by the REST Call invoked just before in the Action Chain.

![](workshops/visualbuilder/media/194.png)

In order to help us in the aggregation, we're going to use the _Lodash_ Javascript library (see [here](https://lodash.com) for more information). VBCS is based on Oracle JET (as mentioned at the beginning of this workshop) and JET uses _RequireJS_ framework as the module and dependencies loader.

To be able to make use of the _Lodash_ library inside our VBCS Javscript code, we just need to leverage _RequireJS_.

The library will be linked to its CDN: `https://cdnjs.cloudflare.com/ajax/libs/lodash.js/4.17.20/lodash.min.js`

In the Javascript code window, type the following:

`define(['https://cdnjs.cloudflare.com/ajax/libs/lodash.js/4.17.20/lodash.min.js'], function(_) {`

![](workshops/visualbuilder/media/195.png)

The `_` parameter we specify, is the way we will reference the library later in the Javascript code.

Now, for each of the two functions, just copy & paste the correspond body as follows:

```
  PageModule.prototype.aggregateDealType = function (arg1) {
    let i = 0;
    let result = _(arg1.items).groupBy('status').map((o,k) => ({
        id: ++i,
        series: k,
        value: o.length,
        group: o[0].repName + " " + o[0].repSurname
      })).value();
    return result;
  };

  PageModule.prototype.aggregateDealAmount = function (arg1) {
    let i = 0;
    let result = _(arg1.items).groupBy('status').map((o,k) => ({
        id: ++i,
        series: k,
        value: _.sumBy(o,'dealAmount'),
        group: ""
      })).value();
    return result;
  };
```

![](workshops/visualbuilder/media/196.png)

We're done with the Javascript code. Go back to the _Action Chain_. Click on the _Assign Variables_ that we included before, to map the result of the JS Code calls to the ADP variables.

Select the _Assign Variable_ action under `Aggregate Deal Type` and click the _Assign_ link on the Properties View on the right. Expand the `pieADP` variable on the right, and drag & drop the result from the `aggregateDealType` to the `data` attribute:

![](workshops/visualbuilder/media/197.png)

Repeat the same operation in the _Assign Variable_ action under `Aggregate Deal Amount` and click the _Assign_ link on the Properties View on the right. Expand the `barADP` variable on the right, and drag & drop the result from the `aggregateDealAmount` to the `data` attribute.

We have the data ready, we just need to add the charts elements to the panel.

Go to the _Page Designer_ tab and make sure you're viewing the Structure View.

Drag & drop **two** _Flex Containers_ in the last existing (and empty as of now) _Flex Container_:

![](workshops/visualbuilder/media/198.png)

Set the _style_ of both to `width:100%`.

In the first one, drag & drop a _Heading_ element and a _Pie Chart_ element:

![](workshops/visualbuilder/media/199.png)

For the _Heading_ element, set the _Text_ to `Deals by Status`, the _Level_ to `H4` and the _Align_ to `Center`.

For the _Pie Chart_ element, go to the _Data_ tab and set the following properties as follows, using the _fx_ button on each them:

-   _Data_: `$variables.pieADP`
-   _Values_: `$current.data.value`

![](workshops/visualbuilder/media/200.png)

Go to the Properties' _General_ tab and click the _+_ button in the _itemTemplate_ slot to select the _Chart Item Template_:

![](workshops/visualbuilder/media/201.png)

If two templates get created, just delete one of them:

![](workshops/visualbuilder/media/202.png)

In the Structure View, select the _Chart Item_ element and set the following properties, always using the _fx_ button:

-   _Group Id_: `[$current.data.group]`  (**DO NOT FORGET** the `[]`!!)
-   _Series Id_: `$current.data.series`

The Pie Chart is all set!

![](workshops/visualbuilder/media/203.png)

In the second _Flex Container__, drag & drop a _Heading_ element and a _Bar Chart_ element:

![](workshops/visualbuilder/media/204.png)

For the _Heading_ element, set the _Text_ to `Deals by Amount`, the _Level_ to `H4` and the _Align_ to `Center`.

For the _Bar Chart_ element, go to the _Data_ tab and set the following properties as follows, using the _fx_ button on each them:

-   _Data_: `$variables.barADP`
-   _Values_: `$current.data.value`
-   _Groups_: `[$current.data.group]`  (**DO NOT FORGET** the `[]`!!)
-   _Series_: `$current.data.series`

You're done with the Bar Chart too and now the application is ready to be published (again).

### Hands On Lab - Step 16: Publish New Version

As we did before, just set the new version first to _Stage_ and then to _Publish_

![](workshops/visualbuilder/media/205.png)
