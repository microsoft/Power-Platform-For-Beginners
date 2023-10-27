# Power Apps Development

## Overview Power Apps

Power Apps is a game-changing addition to Microsoft's Power Platform, designed to bridge the gap between IT professionals and everyday business users. At its core, Power Apps democratizes the process of app development by making it accessible to a broader range of users. Creating a custom business application no longer requires extensive coding knowledge or a background in software development. With Power Apps, even those with limited technical experience can create tailored applications to meet specific business needs.

### Empowering the Non-Technical Users

One of the standout features of Power Apps is its user-friendly interface. It is designed with the modern user in mind and leverages a low-code development environment. This means that users can utilize a more intuitive, drag-and-drop interface rather than delving deep into complex lines of code. Such an approach speeds up the development process and makes it more inclusive. Whether it's a department head wanting to digitize a manual process or a business analyst looking to create a tool for data collection, Power Apps empowers them to transform their ideas into functional apps.

### Seamless Integration with Business Tools

Power Apps is not just an isolated tool; it's part of a broader ecosystem. Microsoft's Power Platform, which includes Power BI, Power Automate, and Power Virtual Agents, offers tools designed to optimize business processes. As a pivotal part of this suite, Power Apps allows for seamless integration with these tools and other Microsoft services like Outlook, SharePoint, Teams, and Dynamics 365. This ensures that users can create applications that are not only functional but can also easily tie into existing systems and workflows, enhancing overall operational efficiency.

### The Future of Business App Development

In the rapidly evolving digital age, businesses must be agile and adaptable. Traditional app development can be time-consuming and often requires a significant resource investment. Power Apps, emphasizing quick, low-code development, represents the future of business app creation. By democratizing the development process and making it accessible to a broader range of users, businesses can swiftly respond to changing needs, innovate processes, and harness the potential of digital transformation.

## Model-Driven vs Canvas Apps

### Canvas Apps

Canvas Apps enables users to design and develop custom applications tailored to their business needs regardless of their technical expertise. One of the significant draws of Canvas Apps is its ability to connect with various data sources, including Microsoft's own Dynamics 365, SharePoint, SQL Server, and many others, ensuring that apps can seamlessly integrate with a user's existing infrastructure. The drag-and-drop functionality and Excel-like low code language ([Power Fx](https://learn.microsoft.com/en-us/power-platform/power-fx/overview)), combined with a myriad of pre-built templates, ensures that individuals without a background in coding can create functional and efficient business applications.
The flexible nature of Canvas Apps facilitates the creation of applications that work across various platforms, including web browsers, tablets, and smartphones. Canvas apps customizability extends to functionality and appearance, meaning that businesses can develop applications that perform the required tasks and align perfectly with their brand requirements.

![Canvas App](/2-Power%20Apps%20Development/assets/expense-report-powerapp.png) 
![Canvas App](/2-Power%20Apps%20Development/assets/MDA-vs-Canvas-fundraiser-app.png)

### Model-Driven Apps

Unlike Canvas Apps, which are focus on the app's user interface, Model-Driven Apps begin with the data model. These apps revolve around core business data and processes, utilizing the [Microsoft Dataverse](https://learn.microsoft.com/power-apps/maker/data-platform/data-platform-intro) to shape the app's behavior and flow. The design is primarily driven by the underlying data structure, components, and relationships, enabling a more standardized yet customizable approach to application creation.
The strength of Model-Driven Apps lies in their ability to automatically generate a responsive UI based on the data model, making them highly adaptive across different devices like tablets, phones, or computers. This approach is especially beneficial for businesses that require complex, data-intensive applications but wish to reduce the time spent on UI design and focus on functionality and business logic.

![Canvas App](/2-Power%20Apps%20Development/assets/MDA-vs-Canvas-main-form-dialog.gif)

### What are the Key Differences?

| Key | Canvas Apps | Model-Driven Apps |
| :--- | :--- | :--- |
| Purpose and Design Approach  | They are designed for creating highly tailored apps with a custom user interface (UI). Developers start with a blank canvas and can design the UI exactly as they want, akin to designing a PowerPoint slide. | These are designed around your core business data and processes. The UI is largely generated based on the underlying data model and the relationships between tables.
| Data Source  | Can connect to multiple data sources, not just the Dataverse. This includes SharePoint, SQL Server, and various other connectors provided by Power Platform.  | Primarily uses the Dataverse  as its data source. |
| User Interface  | Offers pixel-perfect control over the UI. The designer can position, color, and set controls exactly how they want them to appear.  | The UI is automatically generated from the data model. While there's some customization available, it's more constrained than in Canvas Apps. |
| Mobile Capabilities  | Built for both web and mobile. The layout and flow can be specifically designed for mobile scenarios. | Mobile capabilities are present but are more auto-generated based on the underlying data model.  |
| Development Approach | More akin to traditional application design where you focus on the layout, controls, and look-and-feel of the application.  | Focuses more on defining the data model, business rules, and processes. The application's appearance is then generated based on these definitions.  |
| Use Cases  | Ideal for tasks that require a specific UI, such as a company-specific form or a tool that integrates multiple data sources. | Best for applications centered around database tables and relationships, like CRM or ERP solutions where business processes and workflows are key.  |
| Complexity and Learning Curve  |Easier for beginners to start with due to its visual nature, especially those familiar with Microsoft Office tools like PowerPoint.  | Might have a steeper learning curve as understanding the data model, tables, relationships, and business rules is crucial.  |

### Deciding Between Canvas and Model-Driven Apps: Use Cases (examples)

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

Working with data in Power Apps is straightforward. Essentially, you need to select a data source from the available [connectors](https://learn.microsoft.com/connectors/connector-reference/connector-reference-powerapps-connectors), connect to it, and then you can begin working with your data. You have the flexibility to start with various sources such as Excel files, SharePoint lists, Dataverse, SQL databases, and more.

After adding the connector, it will display the tables or lists (referred to as entities) that you can include in your application, all set for your use.

How to add connector?

1. Click on "Data"
2. Click on "Add Data"
3. Search connector you need (ES: SharePoint)
4. Configure connection (if needed)
5. Select Site
6. Select List to use

You can use this step by step guide: [add data to existing app](https://learn.microsoft.com/power-apps/maker/canvas-apps/connections/connection-sharepoint-online#add-data-to-an-existing-app)

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


### Designing User Interfaces in Power Apps Canvas Apps

#### Introduction

The way an application looks and feels is almost as critical as what it does. Users expect seamless experiences, intuitive interactions, and designs that are both functional and aesthetically pleasing. Microsoft's Power Apps Canvas Apps offers the capability to create custom applications with a focus on the user interface (UI). But why is it so important to put significant effort and planning into designing screens?

#### Importance of UI in App Development

- **User Experience (UX) & User Interface (UI)**: While the terms are often used interchangeably, they are distinct. UI is the series of screens, and visual elements (like buttons and icons) that enable a user to interact with a product or service. UX, on the other hand, is the internal experience one has as they interact with every aspect of a product or service. Good UI can lead to good UX, but not necessarily vice versa.

- **First Impressions**: Just like meeting someone for the first time, the initial interaction a user has with an application can shape their entire perception of it. A well-designed, intuitive UI can build trust, encourage users to dive deeper into the app, and boost user retention.

- **Efficiency**: A well-planned UI reduces the time users spend searching for tools or features, leading to faster task completion. This efficiency can translate into increased productivity.

#### Power Apps Canvas Apps: A Canvas for Your Ideas

Canvas Apps in Power Apps allow users to design and develop applications starting with a blank canvas or using one of the pre-defined templates. The design-first approach ensures that the focus remains on the UI, ensuring that the app's design aligns perfectly with the end-user's needs.

#### Designing UI in Canvas Apps

- **Start with the End in Mind**: Before you even begin to drag and drop elements onto your canvas, envision the end result. What do you want your users to achieve? How should they feel while using the app?

- **Templates & Themes**: Power Apps offers various templates and themes to kickstart your design process. These can be beneficial when you're starting, but remember to customize them to your specific needs.

- **Consistency is Key**: Ensure that buttons, colors, fonts, and other UI elements remain consistent throughout the app. This consistency reduces the learning curve and provides a more seamless experience.

- **Feedback Loops**: Implement real-time feedback within your app. Whether it's a button changing color when clicked or a message appearing upon successful form submission, immediate feedback enhances user satisfaction.

- **Mobile-First Design**: Given the increasing use of mobile devices, always consider how your app will look and function on smaller screens.

#### Why Planning Matters

Investing time in planning the UI design process is not about making the application 'look pretty.' It's about:

- **Reducing Development Time**: By having a clear design plan, developers can avoid backtracking or redoing work.
  
- **Enhancing User Satisfaction**: A well-thought-out UI can increase user satisfaction, leading to higher user retention rates.

- **Avoiding Future Complications**: A structured design process can help identify potential problems before they become real issues, saving time and resources in the long run.

#### Conclusion

As you embark on your journey of creating applications with Power Apps Canvas Apps, remember that the UI is not just a superficial layer. It is an integral part of the user's experience and can determine the success or failure of your application. With careful planning and a design-first mindset, you can create applications that are not only functional but also delightful to use.

### Understanding Screens in Power Apps Canvas Apps

#### Introduction to screens

The structure and flow between different sections of your application play a vital role in the overall user experience. In Power Apps Canvas Apps, the primary vehicle for structuring this flow is through screens. However, they are just one of several options available to structure your content and navigate through your app. This chapter delves into the world of screens, how to plan them, and why they aren't always the go-to solution for every content switch.

#### What Are Screens?

Screens in Power Apps Canvas Apps are individual containers for user interface elements. Think of them as distinct pages in a traditional app or website. Each screen can host a variety of controls, data connections, and media elements, giving developers the flexibility to design interactive experiences tailored to each section of their app.

#### Planning Your Screens

- **Define Your App's Flow**: Before you begin adding screens, map out your app's flow. Understanding the user's journey can help you determine how many screens you need and what each one should contain.

- **Keep It Intuitive**: The transition from one screen to another should feel logical to the user. Avoid jumping between unrelated topics or tasks without clear navigational cues.

- **Use Naming Conventions**: As your app grows, you'll thank yourself for using clear, descriptive names for your screens, making them easier to manage and modify.

#### Beyond Screens: Alternative UI Elements

Screens aren't the only way to separate or introduce new content. Using different UI elements can maintain context for the user and provide a smoother experience. Here are some alternatives:

- **Modal Windows**: These are dialog boxes or pop-up windows that appear on top of the current screen. They are excellent for drawing attention to critical actions or information without navigating away from the current context.

- **Sidebars**: Sidebars slide in from the side (usually left or right) of the current screen, offering additional options or information. They're useful for menus, additional controls, or secondary information relevant to the current screen.

- **Tabs**: Tabs allow for the organization of content within the same screen context. Users can easily switch between different sections or categories without the need to transition to an entirely new screen. They are perfect for segmenting related content, like various settings or product categories.

#### Deciding on Screens vs. Other UI Elements

- **Context Preservation**: If you want the user to maintain their current context or not lose sight of the primary content, modal windows or sidebars might be more appropriate than a new screen.

- **Amount of Content**: If you're only displaying a small amount of additional information or controls, it might be overkill to dedicate an entire new screen to it. In such cases, a modal or tab might be more fitting.

- **User Flow**: Consider the user's journey. If the next step in their journey is a significant shift (e.g., moving from a product list to a checkout process), a new screen may be warranted. However, for smaller transitions or sub-steps, other UI elements might suffice.

#### Conclusion

While screens are fundamental building blocks in Power Apps Canvas Apps, it's essential to understand the myriad of UI elements at your disposal. By thoughtfully considering the user's needs, the flow of your app, and the type and amount of content to be displayed, you can create intuitive, efficient, and delightful app experiences, whether they span across multiple screens or elegantly fit within one.

### Creating a New Screen in Power Apps Canvas Apps

#### Introduction

Creating a new screen in Power Apps Canvas Apps is akin to laying down a fresh canvas for a painter. The possibilities are endless. However, with Power Apps, Microsoft provides a range of predefined page designs to speed up development, streamline functionality, and enhance the overall user experience. In this chapter, we'll explore the step-by-step process of creating a new screen and delve into the various page designs available.

#### How to Create a New Screen

1. **Open Power Apps Studio**: Start by launching the Power Apps Studio at [make.powerapps.com](https://make.powerapps.com)

2. **Select Your App**: If you're working on an existing app, open it. For a new app, you can choose to start with a blank app optimized for either phone or tablet or you can leverage the **Start witha page design** feature

![Start with a page design](\assets\create-app-start-page-design.png)

3. **Inserting a Screen**

- Go to the 'Home' tab.
- Click on the 'New Screen' option. A drop-down menu will display the various page designs available.
- Choose your desired design, and the screen will be added to your app.

#### Exploring Different Page Designs

- **Gallery Connected to Table**: This design auto-generates a gallery (a scrollable list) connected to a data table in your app. It's perfect for displaying rows of data, like a list of contacts or products.

- **Gallery Connected to External Data**: Similar to the above, but this design connects to an external data source, like SharePoint, SQL Server, or any other connector supported by Power Apps.

- **Blank Canvas (Tablet or Phone)**: Start with a clean slate, optimized for the device of your choice. This design offers maximum flexibility, letting you drag and drop elements as you see fit.

- **View and Form**: Ideal for data-driven apps, this design provides a view (or gallery) of data items and a detailed form for the selected item. It's useful for applications where users might select an item from a list and then view or edit its details.

- **Blank Page with Navigation**: This design offers a clean page with a predefined navigation bar, facilitating multi-screen navigation for larger apps.

- **Image or Figma File**: Begin with an image or a design imported from Figma as your base. It's beneficial for those who've prototyped their app design in graphic design tools and want to use it as a starting point in Power Apps.

- **Split-Screen**: A design that divides your screen into two parts. It's great for dashboard-style apps or apps where users might need to view two different types of content simultaneously.

- **Sidebar**: This design incorporates a slide-out sidebar, useful for housing menus, additional options, or secondary information.

- **Header-MainSection-Footer**: A classic web-style design with a top header, a central main section, and a bottom footer. This layout is familiar to many users and can provide a structured look to your app.

- **Dashboard**: A design optimized for displaying a summary of data, metrics, or key performance indicators. Dashboards are often used in business or analytic apps to give users an at-a-glance view of critical data.

#### Conclusion

The flexibility of Power Apps Canvas Apps shines through in its diverse screen creation options. Whether you're building a data-heavy application, a dynamic dashboard, or simply need a blank canvas to unleash your creativity, Power Apps provides the tools and templates to get you started. Remember, the choice of page design should align with your app's purpose, the user's needs, and the overall flow you envision.


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
