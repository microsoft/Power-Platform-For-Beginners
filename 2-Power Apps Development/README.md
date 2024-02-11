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

Canvas Apps enables users to design and develop custom applications tailored to their business needs regardless of their technical expertise. One of the significant draws of Canvas Apps is its ability to connect with various data sources, including Microsoft's own Dynamics 365, SharePoint, SQL Server, and many others, ensuring that apps can seamlessly integrate with a user's existing infrastructure. The drag-and-drop functionality and Excel-like low code language ([Power Fx](https://learn.microsoft.com/power-platform/power-fx/overview)), combined with a myriad of pre-built templates, ensures that individuals without a background in coding can create functional and efficient business applications.
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

#### Build an app using Excel
If you're new, you should kwnon that you can create a new App, starting from Excel file. This is a cool feature, usefull, if you:

1. You have an Excel file your're using in your company, and want a quick solution to use manage data with a App.
2. You're new in Power Apps world, and want to have a starting point to build an app.

Before you start, make sure that a table has been defined in the Excel file you want to use. This is an essential requirement for generating the app, starting from an Excel file.

I created a an Excel file, called ["Phonebook.xlsx"](/2-Power%20Apps%20Development/assets/app-from-excel/Phonebook.xlsx) to create our app:

![Excel Data](/2-Power%20Apps%20Development/assets/app-from-excel/excel-data.png)

Let's start! we're going to create our app in less then five minuts:

Once you're logged in to Power Apps environment, click on the home screen and then, click on **"Start with data"** and select **"Upload an Excel file."**

Now we must select Excel file, so choose **"Select from device"** and navigate to the location where your Excel file is stored, select and upload it.

Once the table is created, you can to customize the properties according to your business requirements, then click on "Create app" and wait for the magic.

![Steps to create app from Excel](/2-Power%20Apps%20Development/assets/app-from-excel/steps-to-create-app-from-excel.gif)

The app is ready to use, with the following features:

1. Dataverse table (Yes, your Excel table is Dataverse table now)
2. Show list of records
3. Possibility to filter records
4. CRUD operation

![Our App](/2-Power%20Apps%20Development/assets/app-from-excel/app-from-excel.gif)

Here you can find official documentations: [Create app from data](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/get-started-create-from-data)

##### Build an app using SharePoint

With the same simplicity with which you can create an app starting from an Excel file, as seen in the previous paragraph, you can create an app starting from a SharePoint list.

Even in the case of an app generated from a SharePoint list, you will immediately have access to the following functionalities:

1. In the browse screen, you can scroll through all items in the list.
2. In the details screen, you can show all information about a single item in the list.
3. In the edit screen, you can create an item or update information about an existing item.

The steps to proceed are quite simple:

1. Create a SharePoint list with column you need. You can find an example [here](https://learn.microsoft.com/en-us/sharepoint/dev/business-apps/get-started/set-up-sharepoint-site-lists-libraries#create-projects-list)
2. Sign in to Power Apps
3. Click on create
4. Select "SharePoint"
5. Select connection for SharePoint, if you don't see any connection, click on "New Connection" and create a newone
6. Now you're to be able to find your SharePoint site and your list
7. Select list
8. Click on connect

You can find more details [here](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/app-from-sharepoint)

##### Build an app using Dataverse

After creating an application, either starting from an Excel file or from a SharePoint list, we can automatically generate an application using Dataverse. This capability can be very useful if you need to create a complex application with a real database 'behind the scenes'.

Before start I want to suggest you to do [this training](https://learn.microsoft.com/en-us/training/modules/get-started-with-powerapps-common-data-service/) to understand how to create Table in Dataverse.

If you have Dataverse table ready, you can start:

1. Sign in to Power Apps
2. Click on create
3. Select "Dataverse"
4. Select connection for Dataverse, if you don't see any connection, click on "New Connection" and create a newone
5. Now you're to be able to flooking for your Dataverse table
6. Choose it
7. Click on connect

You can find more details [here](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/data-platform-create-app)

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

#### Conclusion regarding screens

While screens are fundamental building blocks in Power Apps Canvas Apps, it's essential to understand the myriad of UI elements at your disposal. By thoughtfully considering the user's needs, the flow of your app, and the type and amount of content to be displayed, you can create intuitive, efficient, and delightful app experiences, whether they span across multiple screens or elegantly fit within one.

### Creating a New Screen in Power Apps Canvas Apps

#### Introduction to creating screens

Creating a new screen in Power Apps Canvas Apps is akin to laying down a fresh canvas for a painter. The possibilities are endless. However, with Power Apps, Microsoft provides a range of predefined page designs to speed up development, streamline functionality, and enhance the overall user experience. In this chapter, we'll explore the step-by-step process of creating a new screen and delve into the various page designs available.

#### How to Create a New Screen

1. **Open Power Apps Studio**: Start by launching the Power Apps Studio at [make.powerapps.com](https://make.powerapps.com)

2. **Select Your App**: If you're working on an existing app, open it. For a new app, you can choose to start with a blank app optimized for either phone or tablet or you can leverage the **Start witha page design** feature

![Start with a page design](\assets\create-app-start-page-design.png)
3. **Inserting a Screen**

- Go to the **Tree view** tab.
- Select the **New Screen** option. A drop-down menu will display the various page designs available.
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

#### Conclusion to screen options

The flexibility of Power Apps Canvas Apps shines through in its diverse screen creation options. Whether you're building a data-heavy application, a dynamic dashboard, or simply need a blank canvas to unleash your creativity, Power Apps provides the tools and templates to get you started. Remember, the choice of page design should align with your app's purpose, the user's needs, and the overall flow you envision.

### Controls

Currently, we have 2 sets of controls in Power Apps Canvas Apps: Classic controls and Modern Controls.

#### Classic Controls in Power Apps Canvas Apps

##### Introduction to classic controls

Before the introduction of modern controls, Power Apps Canvas Apps heavily relied on what we now refer to as "classic controls". These controls formed the foundational elements that app creators used to design and build applications. Even as the platform evolves, understanding these classic controls remains crucial, as they underpin many existing applications and offer a historical perspective on app development in Power Apps.

##### What Are Classic Controls?

Classic controls in canvas apps are the original set of tools and elements that Microsoft provided to app makers. They were designed to offer flexibility, ease of use, and a wide range of functionalities to cater to different app requirements. From simple buttons and labels to more complex galleries and forms, these controls covered the breadth of common app functionalities.

##### Key Features of Classic Controls

- **Versatility**: The classic controls provided a broad spectrum of tools catering to various application needs – be it data input, display, navigation, or user interaction.

- **Customizability**: App makers had the liberty to customize the appearance, behavior, and interactions of these controls to fit the desired app aesthetics and functionalities.

- **Data Connectivity**: Many of these controls, such as galleries and forms, could easily connect to various data sources, allowing dynamic data display and manipulation.

- **Functionality over Aesthetics**: While customization was possible, the primary focus of classic controls was functionality. Aesthetics and modern design principles became a stronger focus only with the advent of modern controls.

##### Popular Classic Controls

Some of the frequently used classic controls included:

- **Buttons**: Used for triggering actions or navigating between screens.
  
- **Labels**: To display static text or dynamic data.
  
- **Text Input**: Allowed users to input data.

- **Galleries**: Displayed lists of items sourced from data connections like SharePoint, SQL Server, or other connectors.
  
- **Forms**: Used for detailed data viewing, editing, or submission.
  
- **Dropdowns**: Presented users with a list of options to select from.

- **Sliders and Toggles**: Enabled users to make selections based on a range or a binary choice.

##### Transition to Modern Controls

As user experience and design principles evolved, there was a pressing need to update the look and feel of Power Apps to match modern expectations. This led to the introduction of modern controls based on the Fluent design system. However, many existing apps still utilize classic controls, and app makers familiar with these controls might find them more intuitive or suitable for certain scenarios.

##### Considerations when Using Classic Controls

- **Legacy Support**: As Power Apps continues to evolve, there's a possibility that future support or updates for classic controls might be limited.

- **Design Consistency**: When mixing classic and modern controls within an app, designers need to ensure there's a consistent look and feel to prevent a disjointed user experience.

- **Performance**: While classic controls are robust, the new modern controls have been built with a focus on enhanced performance and responsiveness.

##### Conclusion to classic controls

Classic controls in Power Apps Canvas Apps have played a pivotal role in the platform's journey, allowing countless app creators to bring their visions to life. Understanding these controls, their strengths, and their limitations is crucial, especially for those maintaining or updating older applications. As the platform transitions to modern controls, the classic controls serve as a testament to the platform's evolution and the continuous commitment to improvement.

#### Modern Controls in Power Apps Canvas Apps

##### Introduction to modern controls

Embracing the wave of modernity, Microsoft is introducing "modern controls" based on the Fluent 2 design system. This not only simplifies the configuration process but also enhances the overall user experience.

##### What Are Modern Controls?

Modern controls in canvas apps are a revamped set of controls drawing inspiration from the Microsoft Fluent 2 design system. These controls offer:

- **Simplicity**: Easier to configure.
- **Cohesiveness**: They ensure a uniform experience for end-users.
- **Accessibility and Usability**: Designed with these core principles in mind.
- **Performance**: Faster and visually more appealing.
- **Theming**: With the Fluent 2 design system, modern theming becomes more centralized, allowing for an app’s aesthetics to be modified from a singular place.

> **Note**: These features are in preview, implying they are still in the testing phase and might not be suitable for production use yet. However, the aim is to provide users with an opportunity to explore and provide feedback.

##### Enabling Modern Controls and Themes

To harness the power of modern controls in your canvas app:

1. Open your canvas app for editing.
2. On the command bar, choose **Settings** > **Upcoming features**.
3. In the Preview tab, turn on the toggle for **Modern controls and themes**.
4. Access these controls via **Insert** on the app authoring menu. Select **Modern controls** from the list.

Similarly, to explore modern themes, select **Themes** on the app authoring menu.

##### Limitations

As with any preview feature, there are certain limitations:

- Additional steps are required for items added via arrays.
- The property naming convention has a distinct format for modern controls.
- Some properties of the new controls don't mirror the original controls.
- These controls currently don’t support properties visible in the command bar.
- App checker rules don’t function on these controls yet.

These limitations are expected to be addressed as the feature matures.

##### The Promise of Modern Controls

Advancements the modern controls bring:

- **Modern Look**: Fluent design system that's sleek and supports richer interactions.
- **Speed**: Emphasis on performance.
- **Accessibility**: WCAG 2.1 compliant.
- **Theming**: Though not part of the initial rollout, theming and per control styling are on the horizon.

In a side-by-side comparison, the modern controls distinctively stand out, promising a suite of controls that are both stylish and swift. The initial release boasts 13 new controls, but the journey doesn't stop there. Power Apps is set to roll out per control styling, an updated theming system, and a plethora of new controls like toggles, breadcrumbs, and multi-select dropdowns.

##### Engaging with the Modern Controls Feature

To access this feature, developers can activate it within Power Apps Studio through the settings dialog. Upon activation, a list of these controls will be visible on the insert pane.

##### Conclusion to modern controls

The introduction of modern controls in Power Apps Canvas Apps is a testament to Microsoft's commitment to evolving with the demands of modern app development. As these controls transition from preview to production-ready features, they promise to redefine the app-making experience, making it more intuitive, efficient, and delightful.

### Functions

#### 30 Essential Functions in Power Apps Canvas Apps

##### Introduction to functions in Canvas Apps

In Power Apps Canvas Apps, functions are the building blocks that empower app makers to create dynamic and interactive applications. They allow for the manipulation of data, the definition of app behavior, and interaction with various components and data sources. This chapter delves into 30 of the most crucial functions, with examples to illustrate their application.

##### LookUp

**Usage**: Retrieves a single record from a data source.

**Example**: `LookUp(Products, ProductID = 5)` - This fetches the product with the ProductID of 5.

##### Filter

**Usage**: Returns a subset of records based on criteria.

**Example**: `Filter(Orders, OrderDate > DateValue("01-01-2023"))` - Retrieves all orders made after January 1, 2023.

##### Search

**Usage**: Searches for records containing specific text.

**Example**: `Search(Customers, "Doe", "LastName")` - Finds customers with "Doe" in their last name.

##### Sum

**Usage**: Adds up numbers from records.

**Example**: `Sum(Orders, Amount)` - Calculates the total of all order amounts.

##### Patch

**Usage**: Modifies or creates a record in a data source.

**Example**: `Patch(Products, Defaults(Products), {ProductName: "New Product", Price: 10})` - Adds a new product.

##### If

**Usage**: Conditional logic.

**Example**: `If(Age > 21, "Adult", "Minor")` - Returns "Adult" if Age is above 21, otherwise "Minor".

---

##### Switch

**Usage**: Multiple condition checks.

**Example**: `Switch(Status, "New", "Order received", "Shipped", "Order on its way")` - Returns different messages based on order status.

---

##### Navigate

**Usage**: Moves between app screens.

**Example**: `Navigate(Screen2, Fade)` - Navigates to `Screen2` with a fade transition.

---

##### Collect

**Usage**: Adds records to a collection.

**Example**: `Collect(Cart, {ProductID: 101, Quantity: 1})` - Adds a product to the cart.

##### Concatenate

**Usage**: Combines multiple text strings.

**Example**: `Concatenate("Hello, ", UserName)` - Creates a greeting for a user.

##### Len

**Usage**: Returns the length of a text string.

**Example**: `Len(Password) < 8` - Checks if the password is less than 8 characters.

##### Today

**Usage**: Retrieves the current date.

**Example**: `Today()` - Used to fetch the current date.

##### Now

**Usage**: Retrieves the current date and time.

**Example**: `Now()` - Used to fetch the current date and time.

##### User

**Usage**: Provides details about the current app user.

**Example**: `User().Email` - Fetches the email address of the current user.

##### Sort

**Usage**: Orders records based on a column.

**Example**: `Sort(Products, Price, Descending)` - Sorts products by price in descending order.

##### SortByColumns

**Usage**: Orders records based on multiple columns.

**Example**: `SortByColumns(Orders, "OrderDate", Descending, "OrderID", Ascending)` - Sorts by order date, then by order ID.

##### CountRows

**Usage**: Counts the number of records.

**Example**: `CountRows(Filter(Products, Price > 50))` - Counts products priced over $50.

##### IsBlank

**Usage**: Checks if a field is empty.

**Example**: `IsBlank(Email)` - Validates if the email field is empty.

##### Round

**Usage**: Rounds numbers.

**Example**: `Round(Price, 2)` - Rounds a price to two decimal places.

##### Lower & Upper

**Usage**: Converts text to lowercase or uppercase.

**Example**: `Lower(Username)` - Converts a username to lowercase.

##### Text

**Usage**: Converts numbers and dates to text.

**Example**: `Text(Today(), "[$-en-US]dddd, mmmm dd, yyyy")` - Formats the current date.

##### Value

**Usage**: Converts text to number.

**Example**: `Value("123") + 10` - Converts the string "123" to a number and adds 10.

##### Timer

**Usage**: Works with a timer control for actions at intervals.

**Example**: `Timer.Start()` - Starts the timer.

##### Distinct

**Usage**: Retrieves unique values from a column.

**Example**: `Distinct(Orders, Country)` - Lists all unique countries from orders.

##### ForAll

**Usage**: Executes a formula for all records.

**Example**: `ForAll(Products, Patch(Inventory, ThisRecord, {Stock: Stock - 1}))` - Decreases stock by 1 for all products.

##### Gallery.Selected

**Usage**: Retrieves the currently selected item in a gallery.

**Example**: `Gallery1.Selected.ProductName` - Fetches the name of the selected product in `Gallery1`.

##### Reset

**Usage**: Resets a control to its default value.

**Example**: `Reset(TextInput1)` - Resets the text input field `TextInput1`.

##### Defaults

**Usage**: Retrieves the default record structure for a data source.

**Example**: `Patch(Products, Defaults(Products), {ProductName: "New Item"})` - Adds a new product with a default structure.

##### IsNumeric

**Usage**: Checks if a string is a number.

**Example**: `IsNumeric(Input.Text)` - Validates if the input is numeric.

##### With

**Usage**: Creates a local variable for use within a block of formulas.

**Example**: `With({localVar: "Hello"}, Concatenate(localVar, " World"))` - Combines "Hello" with " World".

#### Link to Official Documentation

For a more detailed understanding of these functions, as well as others, please visit the official Microsoft documentation: [Power Apps formula reference](https://learn.microsoft.com/powerapps/maker/canvas-apps/formula-reference).

#### Conclusion to functions

Functions in Power Apps Canvas Apps are indispensable tools that, when used effectively, can transform a simple app into a dynamic and powerful tool. With the understanding of these essential functions, app creators are better equipped to craft intricate workflows, manipulate data, and tailor apps to specific needs. The key lies in experimentation, practice, and a deep dive into the official documentation for nuances and updates.

### Variables in Power Apps Canvas Apps

#### Introduction to variables in Canvas Apps

In Power Apps Canvas Apps, variables play a pivotal role in holding data temporarily, allowing for the dynamic manipulation and presentation of data across screens and controls. Variables can be seen as containers or placeholders that store values, which can then be used and modified throughout an app. Understanding the types of variables and how to employ them efficiently is foundational for anyone looking to create versatile and interactive apps.

#### Global Variables

##### Overview

Global variables are variables that are accessible from any screen within the app. Once a global variable is set, its value remains consistent throughout the app unless altered or cleared.

##### Setting a Global Variable

Use the `Set` function to create or modify a global variable.
Example: `Set(gbl_Greeting, "Hello World")` - This sets the global variable named `gbl_Greeting` to the string "Hello World".

##### Using a Global Variable

Use the variable name wherever required.
Example: In a label's Text property, `gbl_Greeting` would display "Hello World".

##### Clearing a Global Variable

Setting a global variable to blank or resetting the app clears the variable's value.
Example: `Set(gbl_Greeting, Blank())`

#### Context Variables

##### Overview of context variables

Context variables are local to the screen or control where they are used. They're typically employed to pass data between screens.

##### Setting a Context Variable

Use the `Navigate` function with a context argument or the `UpdateContext` function.

- Using `Navigate`: `Navigate(Screen2, None, { ctx_Greeting: "Hello from Screen1" })`
- Using `UpdateContext`: `UpdateContext({ ctx_Greeting: "Hello on this Screen" })`

##### Using a Context Variable

Like global variables, use the variable name to access its value within the context it was set.

##### Clearing a Context Variable

To clear a context variable, you can either navigate away from the screen or use the `UpdateContext` function.
Example: `UpdateContext({ ctx_Greeting: Blank() })`

#### The 'With' Function and Local Variables

##### Overview of the with function

The `With` function is used to create local variables that exist within a specific block of formulas. These variables are especially useful to simplify and optimize formulas by storing values that are used repeatedly.

##### Using the `With` Function

The structure involves defining a local variable and then using it in a subsequent formula.
Example:    `With({ locGreeting: "Hello" }, Concatenate(locGreeting, " World"))`

This would result in "Hello World". The `locGreeting` only exists within the `With` function's context.

#### Good Practices for Variables

1. **Naming Convention**: Adopt a consistent naming convention for variables. For example, use prefixes like "gbl_" for global variables (e.g., `gbl_userName`) and "ctx_" for context variables (e.g., `ctx_orderDetails`).

2. **Limit Global Variables**: Only use global variables for values needed across multiple screens. Excessive use of global variables can make apps harder to manage and debug.

3. **Scope Appropriateness**: Choose the scope of your variable (global, context, local) based on its usage. Avoid using a global variable for something that's only needed on a single screen.

4. **Clear When Done**: Especially for global variables, ensure you clear them when they're no longer needed to free up memory and reduce potential conflicts.

#### Conclusion to variables in Canvas apps

Variables are indispensable when creating interactive and dynamic Canvas Apps in Power Apps. They allow for data storage and manipulation across screens and controls, enabling app makers to craft intricate workflows and offer tailored user experiences. By understanding the types and scopes of variables and adopting best practices, app creators can build efficient and maintainable apps.

### Collections in Power Apps Canvas Apps

#### Introduction to collections in Canvas Apps

Collections are a powerful tool used to store, manipulate, and manage data temporarily. Think of collections as tables in memory that can be filled with rows of data. They can be used to store data from various sources, manipulate it as required, and then use or save that data back to a data source or use it within the app. This chapter aims to provide an in-depth understanding of collections, their creation, use, and best practices.

#### What are Collections?

Collections are temporary tables that exist only while the app is running. They can hold single or multiple records, and each record can have multiple columns. Collections are particularly useful when:

- Working offline and needing to store data temporarily.
- Accumulating data over time, like items in a shopping cart.
- Manipulating data without affecting the original data source.

#### Creating a Collection

Use the `Collect` function to create or add data to a collection.
Example:
`Collect(colOrders, {OrderId: 1, Product: "Laptop", Quantity: 3})`

This creates (or adds to) a collection named `colOrders` with the specified data.

#### Adding Data to a Collection

The same `Collect` function can add more records to an existing collection.
Example: `Collect(colOrders, {OrderId: 2, Product: "Mouse", Quantity: 1})`

#### Clearing a Collection

Use the `Clear` function.
Example: `Clear(colOrders)`

#### Modifying Data

Use the `Patch` function to modify existing records in a collection.
Example:`Patch(colOrders, {OrderId: 2}, {Quantity: 2})`

This modifies the quantity of the order with `OrderId: 2`.

#### Filtering Data

Use the `Filter` function to create a subset of data from a collection based on a condition.
Example:
`Filter(colOrders, Quantity > 1)`

This filters the orders with a quantity greater than one.

#### Sorting Data

Use the `Sort` or `SortByColumns` functions.
Example:
`Sort(colOrders, Product)`

This sorts the collection based on the Product column.

#### Displaying Collection Data

Collections can be easily bound to controls. For instance, a collection can be used as the data source for a gallery, allowing users to scroll through and interact with the data.
Example: Setting a gallery's `Items` property to `colOrders` would display the data from the `colOrders` collection in the gallery.

#### Saving Data

While collections are temporary, you can save their data to a permanent data source using functions like `Patch` or save them to local storage using `SaveData`.

#### Loading Data

For data saved to local storage, use the `LoadData` function to load it back into a collection when the app starts.

#### Good Practices for Collections

1. **Efficient Data Manipulation**: Use collections for temporary data manipulation, ensuring that you don’t unnecessarily load large datasets into collections which can affect app performance.
  
2. **Naming Convention**: Adopt a consistent naming convention, such as prefixing collections with "col_" (e.g., `col_userDetails`).

3. **Regularly Clear Unused Data**: To manage memory efficiently, clear collections that are no longer required.

4. **Remember the Temporary Nature**: Always remember that collections are temporary. If you need to retain data, make sure to save it to a data source or use local storage for offline scenarios.

#### Conclusion to collections

Collections in Power Apps Canvas Apps offer a dynamic way to handle data on-the-fly, making it possible to create intricate data-driven apps without constantly interacting with external data sources. They bridge the gap between raw data and user interactivity, and when utilized effectively, can greatly enhance the efficiency and user experience of an app.

## Model-Driven Apps within the Power Apps Ecosystem

### Introduction to Model-Driven Apps

While both model-driven apps and canvas apps are integral parts of the Microsoft Power Apps platform, they are distinct in their design philosophy and purpose. This chapter will delve into the concept of model-driven apps, their integration with canvas apps, and the unique features they bring to the Power Apps ecosystem.

### What are Model-Driven Apps?

Model-driven apps provide a no-code, component-focused approach to app development. They are built primarily on top of the Microsoft Dataverse and automatically generate great UIs that are responsive across devices.

**Key Features**:

- **Data-centric**: Designed around your core business data and processes.
- **Component-Based**: Built using components like forms, views, and charts.
- **Automatically Responsive**: Adjusts to different devices and screen sizes without additional design effort.

### Canvas Apps vs Model-Driven Apps

While canvas apps allow for pixel-perfect UI/UX design, granting app makers the flexibility to create a bespoke interface, model-driven apps abstract the UI layer, focusing more on the data and processes.

**Differences**:

- **Design Philosophy**: Canvas apps start with the user interface, then connect to data. Model-driven apps begin with the data model and generate the UI.
- **Best Use Cases**: Canvas apps are ideal when a tailored UI/UX is crucial. Model-driven apps shine when dealing with complex data structures and business processes.

### Integrating Model-Driven Apps with Canvas Apps

Canvas apps can be embedded within model-driven apps, combining the strengths of both:

1. **Embedding Canvas Apps**: Create a canvas app that caters to a specific function and embed it into a model-driven app's form or page. This allows for specialized UI/UX tasks within the broader, data-centric environment of the model-driven app.
  
2. **Shared Data Source**: Both app types can share the Microsoft Dataverse, ensuring data consistency and real-time updates.

### Benefits of Using Model-Driven Apps

- **Rapid Development**: With the UI generated from the data model, much of the design work is automated, allowing for faster app creation.
  
- **Complex Business Processes**: Model-driven apps handle complex business logic and processes with ease, leveraging capabilities from the Microsoft Power Platform like Power Automate.
  
- **Unified Data**: Built on the Dataverse, model-driven apps ensure that data is unified, consistent, and easily accessible across the organization.

### Getting Started with Model-Driven Apps

**Steps**:

1. **Define the Data Model**: Begin by defining your entities (tables), attributes (fields), and relationships in the Dataverse.
  
2. **Design Components**: Create or customize forms, views, charts, and dashboards.
  
3. **Define Business Logic**: Implement business rules, workflows, and automated processes using Power Automate.
  
4. **Integrate Canvas Apps (if needed)**: Embed tailored canvas app solutions for specific UI/UX needs.

5. **Test & Deploy**: Use the Power Apps platform to test the app's functionality and then deploy it to users.

### Conclusion to Model-Driven Apps

Model-driven apps represent a powerful, data-centric approach to app development within the Power Apps ecosystem. By understanding when and how to utilize them—alone or in tandem with canvas apps—organizations can streamline processes, enhance data interaction, and rapidly develop robust applications that cater to complex business needs.

### Microsoft Dataverse: The Core of Power Platform Data Management

#### Introduction to Dataverse

Microsoft Dataverse is a key component of the Microsoft Power Platform. As a low-code data platform, Dataverse provides a secure and scalable storage solution for data used in applications like Power Apps, Power Automate, Power BI, and Microsoft Dynamics 365. This chapter will explore the foundations, features, and functionalities of Dataverse.

#### Understanding Microsoft Dataverse

Dataverse is a cloud-based service that provides an environment to store, manage, and secure business data. With its relational data capabilities, it allows for the storage of data in a structured manner, making data retrieval and management streamlined and efficient.

**Key Features**:

- **Rich Data Types**: Supports complex data types, including lookups, option sets, and image.
- **Relational Data Model**: Tables (formerly entities), columns (formerly fields), and relationships define and structure the data.
- **Security**: Robust security model ensures data protection and user-specific data access.
- **Logic & Validation**: Business rules, workflows, and plugins ensure data integrity and automate processes.

#### Key Components of Dataverse

- **Tables**: Store data and consist of rows (records) and columns (fields).
  
- **Columns**: Define the data type and attributes of the data stored.
  
- **Relationships**: Establish connections between tables, allowing for data relationships like one-to-many or many-to-many.
  
- **Choice Columns**: Predefined list of values in a column.
  
- **Views**: Predefined ways to visualize and filter table data.
  
- **Forms**: Designed layouts to interact with table data.

#### Security in Dataverse

Ensuring the safety and appropriate access of data is paramount. Dataverse accomplishes this through:

- **Role-Based Security**: Defines what actions a user can perform based on their role.
  
- **Field-Level Security**: Controls access to specific columns in a table.
  
- **Row-Level Security**: Regulates data access based on business rules, ensuring users see only the rows they need.

#### Integration Capabilities

Dataverse seamlessly integrates with other Microsoft and third-party apps:

- **Power Platform**: Direct integration with Power Apps, Power BI, and Power Automate.
  
- **Dynamics 365**: Serves as the data platform for Microsoft's suite of business apps.
  
- **Azure Services**: Interact and augment with Azure functionalities, from AI to storage.
  
- **Custom Connectors**: Bridge to external systems, data sources, and APIs.

#### Benefits of Using Dataverse

- **Scalability**: Adjusts to fit varying amounts of data and user loads.
  
- **Productivity**: Automate processes and integrate seamlessly with other Microsoft products.
  
- **Flexibility**: Adapt and customize to unique business needs.
  
- **Unified Data**: Provides a central repository, ensuring consistent data across applications.

#### Conclusion to Dataverse

Microsoft Dataverse acts as the backbone for data management within the Power Platform. Its rich features, robust security measures, and flexibility make it a formidable tool for businesses aiming to harness their data effectively. By leveraging Dataverse, organizations can unify, protect, and optimize their data, fostering a conducive environment for growth and innovation.

##### Tables in Microsoft Dataverse: Creation, Challenges, and Good Practices

##### Introduction to tables in Dataverse

In Microsoft Dataverse, tables serve as the foundational building blocks for data storage. They hold the structured data utilized by apps within the Power Platform and beyond. This chapter delves into creating tables in Dataverse, common pitfalls to be wary of, and best practices to adopt.

##### Understanding Tables in Dataverse

At its core, a table in Dataverse (formerly known as an 'entity') is a container for data. Each table consists of rows (records) and columns (fields). The structure and relationships of these tables mirror the complexities and nuances of real-world data.

##### Creating Tables in Dataverse

**Steps to Create a Table**:

1. **Access Dataverse**: Navigate to the [make.powerapps.com](https://make.powerapps,com) and select your environment.
2. **Navigate to Tables**: Within the **Data** section, choose **Tables**.
3. **New Table**: Select **New Table** and provide a name, display name, and primary name column for your table.
4. **Define Columns**: Add columns as required, specifying data type and properties for each.
5. **Establish Relationships**: If needed, create relationships between this table and existing tables.
6. **Save and Publish**: Once you've configured the table, save and publish it.

##### Common Challenges and Their Solutions

- **Data Duplication**: Duplication can arise when tables are not properly designed or when data imports aren't managed correctly. Utilize Dataverse's duplication detection tools to identify and resolve these issues.

- **Poorly Defined Relationships**: Without clear relationships, data retrieval can become complex and slow. Ensure that relationships between tables are logical and well-defined.

- **Over-customization**: Adding too many custom columns or unnecessary tables can lead to a cluttered and inefficient environment. Stick to necessary customizations and periodically review and refine your schema.

##### Good Practices

- **Descriptive Naming**: Use clear, descriptive names for tables and columns. This aids in future development and collaboration.

- **Limit Unused Columns**: Each unused column in a table is a waste of resources. Regularly review tables and remove or hide unnecessary columns.

- **Leverage Metadata**: Metadata provides context about the data. Make use of table and column descriptions to provide clarity to other developers or users.

- **Plan for Scalability**: As your organization grows, so will the data. Design tables keeping scalability in mind, avoiding potential future roadblocks.

- **Backup Regularly**: Changes to table structures can sometimes lead to data loss or corruption. Implement regular backup strategies.

- **Test Before Deploying**: Especially in production environments, thoroughly test changes to tables, columns, and relationships before deploying.

##### Conclusion to creating tables

Tables in Dataverse are central to data management within the Power Platform ecosystem. While creating and managing tables can seem straightforward, attention to detail and adherence to best practices are key. A well-structured Dataverse environment, grounded on efficient tables, ensures that apps and processes run smoothly, reliably, and efficiently.

#### Relationships in Dataverse Tables: Types, Creation, and Good Practices

##### Introduction to Relationships

In Microsoft Dataverse, relationships establish connections between tables, allowing them to interact and share data. This chapter provides a comprehensive guide to the different types of relationships in Dataverse, their creation, examples, and key practices to adopt for optimal use.

##### Types of Relationships in Dataverse

There are primarily three types of relationships in Dataverse:

**One-to-Many (1:N) Relationship**:

- A single record from one table is linked to multiple records in another.
- Example: One customer can place many orders, but each order is associated with only one customer.

**Many-to-One (N:1) Relationship**:

- This is the reverse of a 1:N relationship. Multiple records from one table link to a single record in another table.
- Example: Many orders can be linked to one product, signifying that one product can be ordered multiple times.

**Many-to-Many (N:N) Relationship**:

- Records from one table can relate to multiple records in another table and vice versa.
- Example: Students and courses. One student can enroll in multiple courses, and one course can have multiple students.

##### Creating Relationships

**Steps to Create a Relationship**:

1. **Access Dataverse**: Navigate to [make.powerapps.com](https://make.powerapps,com) and select your environment.
2. **Select Table**: Choose the table you want to create a relationship for.
3. **Define Relationship**: Depending on your requirement, select the appropriate relationship type (1:N, N:1, N:N).
4. **Specify Tables**: Determine the primary (or 'parent') table and the related (or 'child') table.
5. **Configure Fields**: Define which fields are connected through the relationship.
6. **Save and Publish**: Finalize the relationship and make it active.

##### Good Practices for relationships

- **Clear Naming Conventions**: Name relationships descriptively for clarity and easier future management.
  
- **Limit Cascading Rules**: Cascading rules determine how actions like delete or reassign on a primary table affect related tables. Overuse can complicate data management and impact performance.
  
- **Document Relationships**: Maintain documentation of why and how relationships were created, aiding future developers and system architects.

- **Review Relationships Regularly**: As business requirements change, relationships might need to be adjusted, removed, or added.

##### Conclusion to relationships

Establishing relationships between tables in Dataverse is a critical aspect of designing a cohesive and functional data model. By understanding the types of relationships, their appropriate use, and following best practices, you can ensure a robust, efficient, and scalable system.

#### Dataverse Columns: Creation, Types, and Examples

##### Introduction to columns

Columns (previously known as fields) in Dataverse store individual pieces of data for a table, much like how a spreadsheet uses columns to hold data. In this chapter, we'll dive deep into understanding Dataverse columns, the various types available, and how to create them.

##### Creating Columns in Dataverse

**Steps to Create a Column**:

1. **Navigate to Dataverse**: Head to the [make.powerapps.com](https://make.powerapps,com) and select your environment
2. **Choose a Table**: Identify and select the table for which you want to create a column.
3. **Add Column**: Click on the ‘Add column’ option.
4. **Specify Details**:
    - Name the column.
    - Choose the column type.
    - Fill out any additional settings or attributes specific to the column type.
5. **Save and Publish**: Once satisfied, finalize by saving your changes, then publish the table to make the new column available.

##### Types of Columns and Examples

Dataverse provides a rich array of column types to cater to diverse data storage needs. Here's an overview:

**Text**:

- Stores alphanumeric characters.
- Example: `FirstName`, storing values like "John".

**Whole Number**:

- Contains entire numbers without decimals.
- Example: `TotalProductsSold`, with values like 150.

**Decimal Number**:

- Holds numbers with decimals.
- Example: `ProductWeight`, storing values like 2.5.

**Currency**:

- Specifically for monetary values, with precision for currency calculations.
- Example: `ProductPrice`, with values like $25.99.

**Date and Time**:

- Stores dates, times, or both.
- Example: `PurchaseDate`, holding dates like "2023-05-01".

**Choice**:

- Contains a set of predefined options.
- Example: `OrderStatus`, with choices like "Processing", "Shipped", "Delivered".

**Lookup**:

- Establishes a link to another table, allowing for the creation of relationships.
- Example: `CustomerID`, referencing an ID from a Customers table.

**Yes/No**:

- Boolean values.
- Example: `IsProductAvailable`, with values either being Yes or No.

**Image**:

- Holds image data.
- Example: `ProductImage`, containing a picture of a product.

**Floating Point Number**:

- For numbers that can have an immense range of values.
- Example: `ProductRating`, which might store values like 4.3.

**GUID** (Globally Unique Identifier):

- Unique alphanumeric strings used to identify records.
- Example: `RecordID`, with values like "4f50b634-8fb3-43d9-a343-f5f9d909c3d7".

**Customer**:

- A special lookup that can reference either an 'Account' or 'Contact'.
- Example: `PrimaryCustomer`, pointing to a specific account or contact.

**Owner**:

- Relates to users or teams, often used for record ownership or sharing purposes.
- Example: `AssignedAgent`, linking to a specific user in the system.

##### Conclusion to columns

Dataverse columns form the backbone of data storage and manipulation within Power Platform's ecosystem. Understanding the available column types and their purposes helps in designing efficient and meaningful data models. When creating columns, always consider the nature of data to be stored, the kind of operations that might be performed on it, and how it relates to other data in the system.

### Forms
With Power Apps model-driven apps, Dataverse tables forms provide the user interface that people use to interact with the data they need to do their work. It's important that the forms people use are designed to allow them to find or enter the information they need efficiently.

![Form](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/Forms_WhatIsForms_FormExample.png?raw=true)
#### Type of Forms
There are different types of forms, and each type has a specific functionality or use. These include:

* Main (the main user interface).
Used in model-driven apps, Dynamics 365 for tablets, and Dynamics 365 for Outlook.
These forms provide the main user interface for viewing and interacting with table data.
* Quick create (rapid data entry).Used in model-driven apps, Dynamics 365 for tablets, and Dynamics 365 for Outlook.For updated tables, these forms provide a basic form optimized for creating new records.
* Quick view (to see related data).
Used in model-driven apps, Dynamics 365 for tablets, and Dynamics 365 for Outlook. For updated tables, these forms appear within the main form to display additional data for a row that is referenced by a lookup column in the form. Users can view data from related tables without having to leave the form.
* Card form (a compact view).Used in views for model-driven apps. Card forms are designed to present information in a compact format that is suitable for mobile devices.

More information: [Types of forms in Power Apps.](https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/types-forms)

#### Access Dataverse tables' default forms (Forms that are created when the table is created)
Accessing Dataverse tables forms involves a few steps: you can access the forms by going to your tables in the [Power Apps Portal](https://make.powerapps.com) and selecting the Tables menu item on the left panel, then selecting the specific table and finally selecting forms from the table designer. Another way to access the forms is to go to the solution where you have created the table (If you created your table inside a custom solution) and from the object treeview, select tables, then select the table, and then select forms.

![View Forms](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/Forms_ExploreDefaultTableForms_0.gif?raw=true)

![View Forms](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/Forms_ExploreDefaultTableForms.gif?raw=true)

#### Create and/or Edit Forms
When a new form is created for a table, its form type is Main. When the new form opens, it is identical to the form named Information. Columns, sections, tabs, navigation, and properties associated with the form can be edited and the form can then be saved.

Each main form is composed of one or more tabs. Each tab can have one or more sections. Each section contains one or more columns, also called form fields. Forms can be cloned to provide a simpler starting point for form development. To clone a form, open the form you want to copy in the form editor, on the command bar select the down arrow next to Save, select Save As, enter the name for the new form, and then select Save.

1. Sign in to [Power Apps](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

2. Select Tables on the left navigation pane, select the table you want, and then select the Forms area. If the item isn’t in the left navigation pane, select …More and then select the item you want.

3. To create a new main form, on the toolbar select Add form > Main Form.
-OR- To edit an existing main form, select any form with the Type of Main.

What you can do when after creating new form or editing existing form:

#### Change the form design in any of the following ways, as needed:

* Add a column to or remove a column from a form
* Add a section to or remove a section from a form
* Add a tab to or remove a tab from a form
* Add or edit a subgrid on a form
* Edit form headers

#### Edit the properties for parts of the form, as needed:
* Edit form properties
* Edit form column properties
* Edit tab properties
* Edit section properties

![Create Forms](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/Forms_CreateForms.gif?raw=true)

![Edit Forms](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/Forms_EditForm.gif?raw=true)

[Read more about How to create or edit a main form](https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/create-edit-main-forms#how-to-create-or-edit-a-main-form)


### Views
Model-driven apps use views to define how a list of records for a specific table are displayed in the application.

A view defines:

* The columns to display.
* The order of the columns.
* How wide each column should be.
* How the list of records should be sorted by default.
* The default filters applied to restrict the records that will appear.

Once a view has been made available in the app, the user can select it.

![Views](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/Views_switch-views.gif?raw=true)

#### Types of views
There are three types of views: personal, system, and public.

* Personal view - Personal views are owned by individuals and only visible to that person unless they share their personal views with others.
* System view - As a system administrator or system customizer, you can edit system views. System views are special views the application depends on, which exist for system tables or are automatically created when you create custom tables. These views have specific purposes and some additional capabilities.
* Public view - Public views are general purpose views that you can customize as you see fit. They are important because all app users can access them, when they are made available, by using the view selector. It is possible to use public views in subgrids in a form or as a list in a dashboard.

#### Create a View
1-  Sign in to [Power Apps.](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)

2- Select an [environment.](https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/model-driven-app-glossary#environment)

3- Select Tables, and then open the table you want. If the item isn’t in the left navigation pane, select …More and then select the item you want.

4- Select the Views area. If using a custom solution, open the solution, open the table, and then select the Views area.

5- On the toolbar, select Add view.

6- On the Create a view dialog, enter a name and, optionally, a description, and then select Create.

![Create a View](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/Views_CreateView.gif?raw=true)
#### Edit a View
![Edit a View](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/Views_EditView.gif?raw=true)
#### Business rules
You can create business rules and recommendations to apply logic and validations without writing code or creating plug-ins. Business rules provide a simple interface to implement and maintain fast-changing and commonly used rules.

 > Important: Business rules defined for a table apply to both canvas apps and model-driven apps if the table is used in the app. Not all business rule actions are available on canvas apps at this time. More information: [Differences between canvas and model-driven apps](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/data-platform-create-business-rule#differences-between-canvas-and-model-driven-apps)


Very often it is necessary to add in business logic to ensure that columns in a model-driven app are shown, hidden, or set with the correct values. By combining conditions and actions, the following actions are possible with business rules:

* Set column values

* Clear column values

* Set column requirement levels

* Show or hide columns

* Enable or disable columns

* Validate data and show error messages

* Create business recommendations based on business intelligence.

### Create a business rule
1- Sign in to [Power Apps](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), on the left navigation pane, and select Tables. If the item isn’t in the left navigation pane, select […More](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/intro-maker-portal#1--left-navigation-pane) and then select the item you want.

2- Open the table you want to create the business rule for (for example, open the Account table), and then select the Business Rules tab.

3- Select Add business rule.

The business rule designer window opens with a single condition already created for you. Every rule starts with a condition. The business rule takes one or more actions based on that condition.

4- Add a description, if you want, in the description box in the upper-left corner of the window.

5- Set the scope, according to the following:

6- Add conditions. To add more conditions to your business rule:

>a. Drag the Condition component from the Components tab to a plus sign in the designer.


>b. To set properties for the condition, select the Condition component in the designer window, and then set the properties in the Properties tab on the right side of the screen. As you set properties, the Microsoft Dataverse creates an expression at the bottom of the Properties tab.

>c. To add an additional clause (an AND or OR) to the condition, select New in the Properties tab to create a new rule, and then set the properties for that rule. In the Rule Logic column, you can specify whether to add the new rule as an AND or an OR.

>d. When you're done setting properties for the condition, select Apply.

7- Add actions. To add an action:

>a. Drag one of the action components from the Components tab to a plus sign next to Condition component. Drag the action to a plus sign next to a check mark if you want the business rule to take that action when the condition is met, or to a plus sign next to an x if you want the business rule to take that action if the condition isn't met.

>b. To set properties for the action, select the Action component in the designer window, and then set the properties in the Properties tab.

>c. When you're done setting properties, select Apply.

8- Add a business recommendation (model-driven apps only). To add a business recommendation:

>a. Drag the Recommendation component from the Components tab to a plus sign next to a Condition component. Drag the Recommendation component to a plus sign next to a check mark if you want the business rule to take that action when the condition is met, or to a plus sign next to an x if you want the business rule to take that action if the condition isn't met.

>b. To set properties for the recommendation, select the Recommendation component in the designer window, and then set the properties in the Properties tab.

>c. To add more actions to the recommendation, drag them from the Components tab, and then set properties for each action in the Properties tab.

>d. When you're done setting properties, select Apply.

9- To validate the business rule, select Validate on the action bar.

10- To save the business rule, select Save on the action bar.

11- To activate the business rule, select it in the Solution Explorer window, and then select Activate. You can't activate the business rule from the designer window.

![Create Business Rules](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/Create_Business_Rules.gif?raw=true)

![Business Rule Applied](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/Business_Rules_in_Actions.gif?raw=true)
### Business Process flows
Business process flows provide a guide for people to get work done. They provide a streamlined user experience that leads people through the processes their organization has defined for interactions that need to be advanced to a conclusion of some kind. This user experience can be tailored so that people with different security roles can have an experience that best suits the work they do.

Use business process flows to define a set of steps for people to follow to take them to a desired outcome. These steps provide a visual indicator that tells people where they are in the business process. Business process flows reduce the need for training because new users don’t have to focus on which table they should be using. They can let the process guide them. You can configure business process flows to support common sales methodologies that can help your sales groups achieve better results. For service groups, business process flows can help new staff get up-to-speed more quickly and avoid mistakes that could result in unsatisfied customers.
![BPF](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/business-process-stages.png?raw=true)

Each stage contains a group of steps. Each step represents a column where data can be entered. You can advance to the next stage by using the Next Stage button. In the unified interface, you can work with a business process flow stage inside the stage flyout or you can pin it to the side pane. Business process flows doesn't support expanding the stage flyout to the side pane on mobile devices.

You can make a step required so that people must enter data for a corresponding column before they can proceed to the next stage. This is commonly called ”stage-gating”. If you are adding a business-required or system-required column to a business process flow stage, we recommend that you add this column to your form as well.

### Security roles
Security roles define how different users access different types of records. To control access to data and resources, you can create or modify security roles and change the security roles that are assigned to your users.

A user can have multiple security roles. Security role privileges are cumulative. Users are granted the privileges that are available in each role that's assigned to them.

#### Create a security role
1- [Sign in](https://admin.powerplatform.microsoft.com/environments) to the Power Platform admin center and select an environment.

2- Select Settings > Users + permissions > Security roles.

3- Select + New role.

4- Enter a role name.

5- Select a business unit.

6- To allow team members to inherit the privileges of this role when it's assigned to a team, accept the default Member's privilege inheritance setting, which is Direct User (Basic) access level and Team privileges.

7- To use the new role to run model-driven apps, accept the default Include App Opener privileges for running Model-Driven apps setting, which is set to On.

8- Use the new or legacy experience to specify privileges for the security role.

9- Select Save. The properties of the new role are displayed.

> Note: You must grant your app's table privileges to this newly created security role. You also need to review and update the default privileges that were copied from the App Opener security role's minimum privileges for common tasks. There are some privileges that were granted with an Organization-level read access, such as Process (Flows), that allow the user to run system-supplied flows. If your app or user doesn't need to run system-supplied flows, you can change this privilege to User (basic) level.


10- Enter your table name in the Search input field to find your app's table.

11- Select your table and set the Permission settings. Then select the Save button.

 > Note: You may need to repeat the last two steps of this procedure if there is more than one table in your app.

 ![Create Seacurity Role](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/Create%20Security%20Role.gif?raw=true)

 ![Assign Security Role to a user](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/Assign%20Security%20Role%20to%20User.gif?raw=true)

#### Create a security role by Copy Role
1- [Sign in](https://admin.powerplatform.microsoft.com/environments) to the Power Platform admin center and select an environment.

2- Select Settings > Users + permissions > Security roles.

3- Select the security role you want to copy.

4- Select Copy.

5- Enter a name for the new role.

6- Select OK.

7- Use the [new](https://learn.microsoft.com/en-us/power-platform/admin/security-roles-privileges#define-the-privileges-and-properties-of-a-security-role) or [legacy](https://learn.microsoft.com/en-us/power-platform/admin/security-roles-privileges#security-roles-and-the-legacy-ui) experience to specify privileges for the security role.

8- Select Save + close.

#### Edit a security role

Before you edit a security role, make sure you understand the principles of controlling data access.

 > Note: You can't edit the System Administrator security role. Instead, copy the System Administrator security role and make changes to the new role.


1- [Sign in](https://admin.powerplatform.microsoft.com/environments) to the Power Platform admin center and select an environment.

2- Select Settings > Users + permissions > Security roles.

3- Select the security role you want to edit.

4- Use the new or legacy experience to specify privileges for the security role.

5- Select Save + close.


### Build your first Model Driven App
#### Model-driven apps overview
Model-driven app design is an approach that focuses on adding components such as forms, views, and charts and dashboards to tables using an app designer tool. Additionally, [relationships](https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/model-driven-app-glossary#relationship) connect tables together in a way that permits navigation between them and ensures that data is not repeated unnecessarily.

Using the app designer with little or no code, you can build apps that are simple or very complex.

#### Process driven apps
Model-driven apps are especially well suited to process driven apps that are data dense and make it easy for users to move between related records. For example, if you are building an app to manage a complex process, such as onboarding new employees, managing a sales process, or member relationships in an organization such as a bank, a model-driven app is a great choice.

#### Data modeling
While they're called model-driven apps, it is often easier to think of them as data model driven apps. This is because, without a data model housed within Microsoft Dataverse, you can't create a model-driven app.

#### User experience
From the user's perspective, all model-driven apps offer a similar experience, which is both accessible to many users and to the device used. The experience is similar to the diagram shown below.

In this example, the app contains three tables (challenges, ideas, team projects), one dashboard, and multiple charts and views. Users can navigate between the tables using the left pane or via the dashboard.

![MDA](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/model-app-sample.png?raw=true)

#### Build a Model-Driven App
This interactive experience guides new makers through the creation of a model-driven app. Using the modern app designer, anyone can quickly create an app in three simple steps.

1- Name your app.

2- Create a page and add the preselected table to the page.

3- Publish and play your app.

![Create Model Driven App](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/Create%20MDA.gif?raw=true)


### Business Process Flows
#### Why business process flows are used
Business process flows provide a guide for people to get work done. They provide a streamlined user experience that leads people through the processes their organization has defined for interactions that need to be advanced to a conclusion of some kind. This user experience can be tailored so that people with different security roles can have an experience that best suits the work they do.

Use business process flows to define a set of steps for people to follow to take them to a desired outcome. These steps provide a visual indicator that tells people where they are in the business process. Business process flows reduce the need for training because new users don’t have to focus on which table they should be using. They can let the process guide them. You can configure business process flows to support common sales methodologies that can help your sales groups achieve better results. For service groups, business process flows can help new staff get up-to-speed more quickly and avoid mistakes that could result in unsatisfied customers.

#### What business process flows can do
With business process flows, you define a set of stages and steps that are then displayed in a control at the top of the form.

![Business Process Flow](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/business-process-stages.png?raw=true)

#### Create a business process flow
1- In Power Apps or Power Automate, select Solutions from the navigation bar on the left.

2- Select or create a solution to use for the business process flow.

3- Within the solution, select New > Automation > Process > Business process flow. a. Give your flow a Display name and Name (LogicalName). c. Select the table from which the flow will be used. d. Select Create.
![Business Process Flow Element](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/business-process-flow-window-showing-main-elements.png?raw=true)
> The new business process flow is created. You can now edit it with a first single stage created for you.
Business process flow window showing main elements.

4- Add stages. If your users will progress from one business stage to another in the process:

> A) Drag a Stage component from the Components tab and drop it on a + sign in the designer.

![Drag a Business Process Stage](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/drag-business-process-stage.png?raw=true)

> B) To set the properties for a stage, select the stage, and then set the properties in the Properties tab on the right side of the screen:

* Enter a display name.

* If desired, select a category for the stage. The category (such as Qualify or Develop), appears as a chevron in the process bar.
![Business Process Bar Chevron](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/business-process-bar-chevron.png?raw=true)

* When you're done changing properties, select the Apply button.

5- Add steps to a stage. To see the steps in a stage, select Details in the lower-right corner of the stage. To add more steps:

> A) Drag the Step component to the stage from the Components tab.

![Add Step Stage to Business Process](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/add-step-stage-business-process.png?raw=true)


> B Select the step, and then set properties in the Properties tab:

* Enter a display name for the step.
* If you want users to enter data to complete a step, select the appropriate column from the drop-down list.
* Select Required if people must fill in the column to complete the step before moving to the next stage of the process.
* Select Apply when you're done.
 > Note: if you set a two-option boolean column as Required, users can't continue unless the column value is Yes. The user is required to mark the column as completed before moving to the next stage.
If either Yes or No are acceptable column values, then you should make the column a choice instead of a two-option boolean column.


6- Add a branch (condition) to the process. To add a branching condition:

> A Drag the Condition component from the Components tab to a + sign between two stages.

![Add Condition to Business Process Flow](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/add-condition-business-process-flow.png?raw=true)


> B Select the condition, and then set properties in the Properties tab. For more information on branching properties, go to Enhance business process flows with branching. When you're finished setting properties for the condition, select Apply.

7- Add a workflow. To invoke a workflow:

> A) Drag a Workflow component from the Components tab to a stage or to the Global Workflow item in the designer. Which one you add it to depends on the following:

* Drag it to a stage when you want to trigger the workflow on entry or exit of the stage. The workflow component must be based on the same primary table as the stage.
* Drag it to the Global Workflow item when you want to trigger the workflow when the process is activated or when the process is archived (when the status changes to Completed or Abandoned). The workflow component must be based on the same primary table as the process.
> B) Select the workflow, and then set properties in the Properties tab:

* Enter a display name.
* Select when the workflow should be triggered.
* Search for an existing on-demand active workflow that matches the stage table or create a new workflow by selecting New.
* Select Apply when you're done.


8- To validate the business process flow, select Validate on the action bar.

9- To save the process as a draft while you continue to work on it, select Save in the action bar.

10- To activate the process and make it available to your team, select Activate on the action bar.

#### How to create Business Process Flow:
![How to create BPF](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/Orders%20BPF.gif?raw=true)

#### See Business Process Flow in action:
![BPF in Action](https://github.com/AhmedSalih-PowerPlatformPlace/Power-Platform-For-Beginners/blob/main/2-Power%20Apps%20Development/assets/BPF%20in%20Action.gif?raw=true)

## Licensing

### Introduction to Licensing

#### Canvas Apps with Standard connectors

#### Canvas Apps with Premium connectors

#### Model Driven Apps Licensing
