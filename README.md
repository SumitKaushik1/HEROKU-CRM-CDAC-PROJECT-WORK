# HEROKU-CRM-CDAC-PROJECT-WORK


## Browser Link
https://crm-app-7461b311cf95.herokuapp.com/Welcome.jsp

## Login Credentials 
- login id - u1111111111
- Login Role Id - r1111111111
- First Name - sumit
- Last Name - kaushik
- Password - Sumit@123



## CRM Application/CRM
This folder contains the source code for the CRM Application.

## apache-tomcat-9.0.36   
This folder contains the apache tomcat server  for the CRM Application.

## Features
[screen-capture.webm](https://github.com/SumitKaushik1/CDAC-PROJECT-CRM-JSP-JAVABEAN-MYSQL/assets/110432346/43750252-264c-4305-8d74-949c59417610)

  ### CRM Application Overview:
   
<p>


Our CRM (Customer Relationship Management) application is designed to streamline customer interactions, manage product information, and optimize sales team performance. It serves as a centralized platform for organizing customer data, tracking sales activities, and facilitating communication between sales representatives and clients.

### Customer Management:

- **Customer Details:**
  The CRM stores comprehensive information about each customer, including their ID, first name, last name, contact details such as mobile number and email, and physical address.
- **Interaction History:**
  It tracks all interactions with customers, ranging from phone calls and emails to meetings and purchases, providing a complete view of the customer's journey.
Segmentation: The CRM allows for segmentation of customers based on various criteria, enabling targeted marketing campaigns and personalized communication.

### Product Management:

- **Product Catalog:**
Our application maintains a catalog of products, detailing each product's ID, type, name, quantity available, and description.
Inventory Management: It keeps track of product inventory in real-time, ensuring accurate stock levels and timely replenishment.
- **Sales and Marketing Support:**
  The CRM utilizes product information to support sales presentations, marketing initiatives, and promotions, helping sales representatives effectively communicate product features and benefits to customers.

### Salesman Management:
- **Salesman Information:**
   The CRM stores information about sales representatives, including their ID, first name, last name, contact details, and address.
- **Schedule Management:** It enables sales representatives to manage their schedules efficiently, including appointments, meetings, and other tasks.
Performance Tracking: Managers can track sales team performance metrics, such as sales targets, leads generated, and deals closed, providing insights to optimize sales strategies and allocate resources effectively.

### Functionality Highlights:

- **Lead Management:** Our CRM captures and tracks leads from various sources, assigns them to sales representatives, and nurtures them through the sales funnel until conversion.
Opportunity Management: It facilitates the management of sales opportunities, allowing sales representatives to track their progress and forecast potential revenue.
Reporting and Analytics: The CRM generates reports and provides analytics to gain insights into customer behavior, sales trends, and team performance, empowering data-driven decision-making.
- **Integration:** Our application seamlessly integrates with other systems such as email, marketing automation, and accounting software, ensuring smooth data flow and process automation across the organization.

### Example Use Case:

-  A sales representative logs into the CRM system and views their schedule for the day, which includes client meetings and follow-up calls.
  They access customer profiles to review past interactions and preferences before the meeting, enabling them to tailor their approach effectively.
  During the meeting, they showcase relevant products based on the customer's needs and preferences, leveraging the CRM's product catalog and inventory information.
- After the meeting, they schedule follow-up tasks and set reminders for future engagements, ensuring timely follow-up and nurturing of leads.

### Conclusion:

In summary, our CRM application serves as a comprehensive solution for managing customer relationships, optimizing sales processes, and driving business growth. By leveraging the provided details, we create a platform that empowers sales teams to deliver exceptional customer experiences, increase efficiency, and achieve sales targets effectively.</p>


## Folder Structure Of The CRM Application Maven Project

When deploying a Java web application on Heroku, especially one built using Maven, you need to ensure that your folder structure is compatible with Heroku’s deployment process. Below is the typical folder structure for deploying a Java-based project (like a web dynamic project) on Heroku.

- Root Directory Structure
Here is the general folder structure for your project:


## Project Structure

```bash
/my-web-app
│
├── /src
│   ├── /main
│   │   ├── /java              # Your Java source code
│   │   ├── /resources         # Application resources (e.g., config files)
│   │   └── /webapp            # JSP, HTML, CSS, JavaScript, WEB-INF directory
│   │       ├── /WEB-INF
│   │       │   ├── web.xml    # Deployment descriptor
│   │       └── /views         # JSP pages or static resources
│   └── /test                  # Test source code (JUnit or TestNG tests)
│
├── /target                    # Auto-generated files (compiled code, JAR, or WAR)
│   ├── /dependency
│   └── my-web-app.war          # Generated WAR file after Maven build
│
├── pom.xml                     # Maven configuration file (dependencies, plugins)
├── Procfile                    # Heroku configuration (how to run your app)
├── system.properties           # Specifies the Java version
└── .gitignore                  # Git ignore rules
`````
-  Key Components
-   src/main/java
This is where your Java source code resides. Place your packages and class files under this directory.

-  src/main/resources
Any non-code resources (like property files, configuration files, etc.) should be placed in this directory.

- src/main/webapp
This folder contains your web assets, such as JSP files, static resources (CSS, JavaScript, images), and the WEB-INF directory where you have web.xml (the deployment descriptor).

- WEB-INF: This folder holds web.xml and your compiled classes (once built).
- pom.xml
This is your Maven configuration file. It includes all the dependencies, build plugins, and configurations for your project. Make sure it includes all necessary dependencies for running the project on Heroku.

- Procfile
The Procfile defines how Heroku should run your app. For a web dynamic project, especially if you’re deploying a WAR file, the content typically looks like this:

- web: java $JAVA_OPTS -jar target/dependency/webapp-runner.jar --port $PORT target/*.war
- system.properties
This file specifies the Java version used on Heroku. Example content:

- Copy code
java.runtime.version=11
- target/
This is the Maven build output folder. After running mvn clean install, Maven generates the WAR file here, which will be deployed to Heroku. The WAR file can be found in the target/ directory as my-web-app.war.

- .gitignore
You should configure the .gitignore file to ignore unnecessary files (such as target/ and *.class files) when pushing your project to Heroku via Git.
