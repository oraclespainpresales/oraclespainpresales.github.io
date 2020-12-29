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

### Application Testing and Lifecycle

You have two options to test your Web application:

![](workshops/visualbuilder/media/39.png)

1.  While you have your page opened in the Page Editor canvas, click the `Live` button from the toolbar (top-right). You'll notice the canvas will be now surronded by a green rectangle. That means the canvas is now in _Live Mode_, and you can interact with the UI components as if the application were deployed. This option is very convenient for quick tests in your page.
    You also have a keyboard shortcut to temporary enable the _Live Mode_: hold the CTRL key (or CMD on Mac)
2.  Click the _Play_ button on the Visual Application toolbar (top-right). The whole application will be opened in preview mode in a new tab in your browser. You can notice that the app URL includes the version number and the mode (preview)

#### Application Lifecycle

A Visual Application can be easily versioned from the application browser. You'll get to the application browser when you login to Visual Builder or, if you have an application already opened, by clicking the top-left hamburger icon and then click All Applications to close the current one and open the application browser:

![](workshops/visualbuilder/media/40.png)

![](workshops/visualbuilder/media/41.png)

Each **application** may have one or multiple versions and **each version** may have three status:

-   **Development**: In the development stage you design your application by building pages and creating business objects. You also use development versions to update the application to fix any problems revealed while testing the application.
-   **Staging**: You use the staged application to prepare the application for publication. You can distribute the URI of the staged application to team members who can help you test the behavior of the application, identify where it can be improved and to test your changes. You can re-stage a version as many times as you need.
-   **Live**: Each time that you are ready to publish a new version of your application you should lock the live version of your application until the new version is published. You cannot make changes to a version of an application after it is published and live. To make additional changes to the application you need to create a new version. The URL of a Live application **does not change from version to version**.

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

### Hands On Lab - Step 5: Add List Component and retrieve BO data

To display the deal information, we're going to use a `List` component.

In the `Components` tab, scroll down until the `Collection` section and drag & drop the `List View` component into the canvas:

![](workshops/visualbuilder/media/82.png)

![](workshops/visualbuilder/media/83.png)

Once added, you can review the page structure and hierarchy of the different components you keep adding. When you add a new component, you can drag & drop it to the canvas or to the structure tree to position it exactly where you want:

![](workshops/visualbuilder/media/84.png)

You can also view (and edit!) the HTML source code of the page by clicking the `Code` button:

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
3.  `dealAmount` (set its type as _Currency_)
4.  `customer`
5.  `dealDate` (set its type as _Input Date_)

Also, drag & drop the field `status` in the _Include in row data_ box on the right. Then click _Next_:

![](workshops/visualbuilder/media/90.png)

On the last step of the wizard you can set a generic filter, sorting and other parameters in the Data Source, but we'll leave this as-is. Just click _Finish_:

![](workshops/visualbuilder/media/91.png)

You now can see how after setting the List View's data source, the data is refreshed in real-time even in the design page, based on the bindings you have just specified in the wizard:

![](workshops/visualbuilder/media/92.png)

### Hands On Lab - Step 6: Test what you have done so far

Although you see the life data during design time, let's bring the Preview feature of VBCS.

Whenever you want during the development of an application, as explained before in the _Application Testing and Lifecycle_ section, you can click the _Live_ button from the toolbar or click the _Play_ button on the Visual Application toolbar (top-right).

![](workshops/visualbuilder/media/39.png)

Do so and review what you have done so far.

### Hands On Lab - Step 7: Include Avatar picture in table

It'd be nice to add an actual picture of the sales rep of each deal entry on the table. We can do so very easily following the next steps.

First, download this [file](https://github.com/oraclespainpresales/oraclespainpresales.github.io/raw/master/workshops/visualbuilder/artifacts/avatars.zip) to your desktop. Then, in the Application Structure view, open the _Resources_ folder and right-click in the _images_ subfolder to finally click the _Import_ menu:

![](workshops/visualbuilder/media/93.png)

Select or drag & drop the previously downloaded `avatar.zip` file and click _Import_. VBCS will unzip the contents automatically:

![](workshops/visualbuilder/media/94.png)

You can see all images imported if you expand the _images_ folder:

![](workshops/visualbuilder/media/95.png)

With all avatars already imported in the app, let's add the avatar image in the existing List View component.

To do so, simply locate the _Avatar_ component in the palette, and drag & drop it on top of the `List View` component either in the Structure view or in the canvas.

**IMPORTANT**: make sure you drop the component in the _image slot_. First drag the _Avatar_ component over the `List item` until the slot popup appears; then, without yet dropping it, move the _Avatar_ component to the _image_ slot:

![](workshops/visualbuilder/media/96.png)

However, you still see a black square. Let's bind the _data_ (source) of the new avatar component to the right picture.

If you reviewed the uploaded images, you probable have noticed each image filename corresponds to a `NameSurname.jpg` pattern. No need to say that the connatenation of the `repName` and `repSurname` fields plus `.jpg` will make the trick!

So, select the avatar component in the Structure view (or select the black square in the canvas) to open its properties section. Go to the _Data_ tab and click the _Src_ field's Expression Editor (`fx` icon):

![](workshops/visualbuilder/media/97.png)

type the following value:

`$application.path + 'resources/images/' + $current.data.repName + $current.data.repSurname + '.jpg'`

![](workshops/visualbuilder/media/98.png)

Finally, go to the _General_ tab and set the _Size_ to `Extra Small`:

![](workshops/visualbuilder/media/99.png)

Now, the list already looks much better!

### Hands On Lab - Step 8: Improve data visualization with CSS

### Hands On Lab - Step 9: Add filter from external service

### Hands On Lab - Step 10: 

### Hands On Lab - Step 11: 



