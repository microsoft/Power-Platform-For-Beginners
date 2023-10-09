# Power Apps Development

## Overview Power Apps

### Model-Driven vs Canvas Apps
#### Canvas Apps:
Canvas Apps allow users to create custom applications starting with a blank canvas, akin to designing a PowerPoint slide. They provide a drag-and-drop interface to design the user interface (UI) pixel-perfectly and can connect to various data sources.

#### Model-Driven Apps:
Model-driven apps are designed around core business data (typically from Microsoft Dataverse) and the processes associated with that data. The application's UI is largely auto-generated based on the underlying data model, including tables, fields, and their relationships. They are more focused on business processes and workflows, and the UI reflects the structure of the underlying data.

#### What are the Key Differences?
| Key | Canvas Apps | Model-Driven Apps |
| ------------- | ------------- | ------------- |
| Purpose and Design Approach  | They are designed for creating highly tailored apps with a custom user interface (UI). Developers start with a blank canvas and can design the UI exactly as they want, akin to designing a PowerPoint slide. | These are designed around your core business data (often from the Dataverse, now part of Microsoft Dataverse) and processes. The UI is largely generated based on the underlying data model and the relationships between entities.
| Data Source  | Can connect to multiple data sources, not just the Dataverse. This includes SharePoint, SQL Server, and various other connectors provided by Power Platform.  | Primarily uses the Dataverse  as its data source. |
| User Interface  | Offers pixel-perfect control over the UI. The designer can position, color, and set controls exactly how they want them to appear.  | The UI is automatically generated from the data model. While there's some customization available, it's more constrained than in Canvas Apps. |
| Mobile Capabilities  | Built for both web and mobile. The layout and flow can be specifically designed for mobile scenarios. | Mobile capabilities are present but are more auto-generated based on the underlying data model.  |
| Development Approach | More akin to traditional application design where you focus on the layout, controls, and look-and-feel of the application.  | Focuses more on defining the data model, business rules, and processes. The application's appearance is then generated based on these definitions.  |
| Use Cases  | Ideal for tasks that require a specific UI, such as a company-specific form or a tool that integrates multiple data sources. | Best for applications centered around database entities and relationships, like CRM or ERP solutions where business processes and workflows are key.  |
| Complexity and Learning Curve  |Easier for beginners to start with due to its visual nature, especially those familiar with Microsoft Office tools like PowerPoint.  | Might have a steeper learning curve as understanding the data model, entities, relationships, and business rules is crucial.  |


#### Deciding Between Canvas and Model-Driven Apps: Use Cases and Guidelines
<!-- - Ahmed -->

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
<!-- - Angelo -->

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
