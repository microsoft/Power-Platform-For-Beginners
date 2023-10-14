# Power Apps Development

## Overview Power Apps
Power Apps is a game-changing addition to Microsoft's Power Platform, designed to bridge the gap between IT professionals and everyday business users. At its core, Power Apps democratizes the process of app development by making it accessible to a broader range of users. Creating a custom business application no longer requires extensive coding knowledge or a background in software development. With Power Apps, even those with limited technical experience can create tailored applications to meet specific business needs.
#### Empowering the Non-Technical Users
One of the standout features of Power Apps is its user-friendly interface. It is designed with the modern user in mind and leverages a low-code development environment. This means that users can utilize a more intuitive, drag-and-drop interface rather than delving deep into complex lines of code. Such an approach speeds up the development process and makes it more inclusive. Whether it's a department head wanting to digitize a manual process or a business analyst looking to create a tool for data collection, Power Apps empowers them to transform their ideas into functional apps.

#### Seamless Integration with Business Tools
Power Apps is not just an isolated tool; it's part of a broader ecosystem. Microsoft's Power Platform, which includes Power BI, Power Automate, and Power Virtual Agents, offers tools designed to optimize business processes. As a pivotal part of this suite, Power Apps allows for seamless integration with these tools and other Microsoft services like Outlook, SharePoint, Teams, and Dynamics 365. This ensures that users can create applications that are not only functional but can also easily tie into existing systems and workflows, enhancing overall operational efficiency.

#### The Future of Business App Development
In the rapidly evolving digital age, businesses must be agile and adaptable. Traditional app development can be time-consuming and often requires a significant resource investment. Power Apps, emphasizing quick, low-code development, represents the future of business app creation. By democratizing the development process and making it accessible to a broader range of users, businesses can swiftly respond to changing needs, innovate processes, and harness the potential of digital transformation.

### Model-Driven vs Canvas Apps
#### Canvas Apps:
Canvas Apps enables users to design and develop custom applications tailored to their business needs regardless of their technical expertise. One of the significant draws of Canvas Apps is its ability to connect with various data sources, including Microsoft's own Dynamics 365, SharePoint, SQL Server, and many others, ensuring that apps can seamlessly integrate with a user's existing infrastructure. The drag-and-drop functionality and Excel-like low code language ([Power Fx](https://learn.microsoft.com/en-us/power-platform/power-fx/overview)), combined with a myriad of pre-built templates, ensures that individuals without a background in coding can create functional and efficient business applications.
The flexible nature of Canvas Apps facilitates the creation of applications that work across various platforms, including web browsers, tablets, and smartphones. Canvas apps customizability extends to functionality and appearance, meaning that businesses can develop applications that perform the required tasks and align perfectly with their brand requirements.

![Canvas App](/2-Power%20Apps%20Development/assets/expense-report-powerapp.png) 
![Canvas App](/2-Power%20Apps%20Development/assets/MDA-vs-Canvas-fundraiser-app.png)

#### Model-Driven Apps:
Unlike Canvas Apps, which are focus on the app's user interface, Model-Driven Apps begin with the data model. These apps revolve around core business data and processes, utilizing the [Microsoft Dataverse](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/data-platform-intro) to shape the app's behavior and flow. The design is primarily driven by the underlying data structure, components, and relationships, enabling a more standardized yet customizable approach to application creation.
The strength of Model-Driven Apps lies in their ability to automatically generate a responsive UI based on the data model, making them highly adaptive across different devices like tablets, phones, or computers. This approach is especially beneficial for businesses that require complex, data-intensive applications but wish to reduce the time spent on UI design and focus on functionality and business logic.

![Canvas App](/2-Power%20Apps%20Development/assets/MDA-vs-Canvas-main-form-dialog.gif)

#### What are the Key Differences?
| Key | Canvas Apps | Model-Driven Apps |
| :--- | :--- | :--- |
| Purpose and Design Approach  | They are designed for creating highly tailored apps with a custom user interface (UI). Developers start with a blank canvas and can design the UI exactly as they want, akin to designing a PowerPoint slide. | These are designed around your core business data and processes. The UI is largely generated based on the underlying data model and the relationships between tables.
| Data Source  | Can connect to multiple data sources, not just the Dataverse. This includes SharePoint, SQL Server, and various other connectors provided by Power Platform.  | Primarily uses the Dataverse  as its data source. |
| User Interface  | Offers pixel-perfect control over the UI. The designer can position, color, and set controls exactly how they want them to appear.  | The UI is automatically generated from the data model. While there's some customization available, it's more constrained than in Canvas Apps. |
| Mobile Capabilities  | Built for both web and mobile. The layout and flow can be specifically designed for mobile scenarios. | Mobile capabilities are present but are more auto-generated based on the underlying data model.  |
| Development Approach | More akin to traditional application design where you focus on the layout, controls, and look-and-feel of the application.  | Focuses more on defining the data model, business rules, and processes. The application's appearance is then generated based on these definitions.  |
| Use Cases  | Ideal for tasks that require a specific UI, such as a company-specific form or a tool that integrates multiple data sources. | Best for applications centered around database tables and relationships, like CRM or ERP solutions where business processes and workflows are key.  |
| Complexity and Learning Curve  |Easier for beginners to start with due to its visual nature, especially those familiar with Microsoft Office tools like PowerPoint.  | Might have a steeper learning curve as understanding the data model, tables, relationships, and business rules is crucial.  |


#### Deciding Between Canvas and Model-Driven Apps: Use Cases (examples)
| Use Case | Canvas Apps | Use Case | Model-Driven Apps |
| :--- | :--- | :--- | :--- |
| Field Service Tool | A utility company might use Canvas Apps to create a mobile tool for technicians in the field. The app could pull data from various sources, like weather forecasts, client databases, and equipment inventories, providing a customized interface for technicians to report statuses, request parts, and communicate with the main office. | Sales CRM | Companies can leverage Model-Driven Apps to manage leads, opportunities, and accounts. The app would automatically generate forms and views based on the sales data model, allowing sales teams to track and nurture potential clients efficiently. |
| Event Registration | For an organization hosting events, a Canvas App can provide a tailored registration experience, integrating with a seating chart, dietary preferences database, and payment gateway. | Case Management | For customer support departments, a Model-Driven App could be used to manage incoming cases, assign them to agents, track resolution timelines, and maintain a knowledge base. |
| Retail Inventory Checker | Retail stores can use Canvas Apps to develop a tablet application for staff to quickly check product availability, integrating with both their stock database and an online product catalog. | Vendor Management | Organizations can track all interactions, contracts, and procurement with vendors in a centralized system, with automatic workflows to handle approval processes. |
| Feedback Collection | A restaurant or cafe could have a kiosk or tablet with a Canvas App for customers to provide feedback, rate their experience, or join a loyalty program. | Regulatory Compliance | In sectors like finance or healthcare, companies could use Model-Driven Apps to ensure adherence to regulations, track any discrepancies, and manage audits. |
| Employee Onboarding | Companies might develop an app tailored to the new employee experience, integrating with training videos, HR policies, and interactive quizzes. | Project Management | While managing large projects, companies can use Model-Driven Apps to keep track of timelines, deliverables, stakeholders, and budgets, leveraging the power of data relationships and views. |

### How Power Apps are usually part of bigger solutions
<!-- - Rebekka -->

### Use cases and examples
<!-- - Rebekka -->

## Canvas Apps

<!-- - Exploring app templates and design principles.
- Creating user interfaces with galleries, forms, and controls.
- Working with data sources, formulas, and variables.
- Implementing navigation and user experience enhancements.
- Integrating with external systems and services. -->

### Building

#### Create your first "Hello World!" Power App
<!-- - Make app in solution
- Getting to know the Canvas App Studio
- incl Save and auto save 
- Rebekka -->

#### Adding data to your App
Working with data in Power Apps is straightforward. Essentially, you need to select a data source from the available [connectors](https://learn.microsoft.com/en-us/connectors/connector-reference/connector-reference-powerapps-connectors), connect to it, and then you can begin working with your data. You have the flexibility to start with various sources such as Excel files, SharePoint lists, Dataverse, SQL databases, and more.

After adding the connector, it will display the tables or lists (referred to as entities) that you can include in your application, all set for your use.

How to add connector?

1. Click on "Data"
2. Click on "Add Data"
3. Search connector you need (ES: SharePoint)
4. Configure connection (if needed)
5. Select Site
6. Select List to use

You can use this step by step guide: [add data to existing app](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/connections/connection-sharepoint-online#add-data-to-an-existing-app)


##### Build an app using Excel
<!-- - Angelo -->

##### Build an app using SharePoint
<!-- - Angelo -->

##### Build an app using Dataverse
<!-- - Use sample data and show how to add that.  
- Angelo -->

#### Building an App that contains Media

#### Adding navigation to your App

#### Adding logic to your app

#### Publishing and running your app
<!-- - Version history -->

### UI

#### Screens

##### how to create a new screen

##### Screen layouts and templates

##### Explain key properties and what they do of popular controls

![Power Apps maker portal popular controls](/2-Power%20Apps%20Development/assets/studio_popularControls.png)

(without form)

#### TextLabel

#### Textinput

#### Datepicker

#### Gallery

#### Rectangle

#### Buttons

### Functions
<!-- - When to you use what
- How to work with the functions documentation-->

### variables and collections

#### Global variables

#### Context variables

#### Collections

## Model Driven Apps

### Dataverse

#### Tables

#### Columns

#### Relationships

#### Forms

#### Views

#### Business rules

#### Business Process flows

#### Recurity roles

### Build

#### Build your first Model Driven App

#### Business Process flows

## Licensing

### Introduction

#### Canvas Apps with Standard connectors

#### Canvas Apps with Premium connectors

#### Model Driven Apps
