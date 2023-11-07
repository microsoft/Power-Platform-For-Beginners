# Power BI

   - Understanding data visualization principles and best practices.
   - Connecting to various data sources and transforming data.
   - Creating interactive reports and dashboards.
   - Implementing data modeling and calculations.
   - Sharing and collaborating on Power BI content.

<br />
<br />

# Power BI for Beginner – Chess Game Analysis 

   - Written by Jihwan Kim | Microsoft MVP 

<br />
<br />

## Contents

#### [1. Opening & Sample data](#chapter1)
#### [2. Unlocking the power of Power BI](#chapter2)
#### [3. Datamodel](#chapter3)
#### [4. Open Power BI Desktop](#chapter4)
#### [5. DAX measures and Visualizations (Proof Of Concept)](#chapter5)
#### [6. DAX measures and Visualizations (Production)](#chapter6)
#### [7. Publishing and Sharing Power BI report](#chapter7)
#### [8. Closing](#chapter8)

<br />
<br />

## <a name="chapter1"></a>1. Opening & Sample data: Online Chess Games 

### Opening statement
Welcome to the world of Power BI for Beginners - Chess Game Analysis! This course is designed with newcomers in mind, but I want to be upfront with you: as we delve into the intricacies of Power BI, M code, and DAX code, you might find it a little more challenging than you initially expected. However, fear not, for the journey of analyzing chess data, deciphering winning moves, and uncovering the excitement within is worth every effort. I've put extra care into providing clear explanations, intuitive comments, and plenty of images to ensure this article is as reader-friendly as possible. So, let's embark on this adventure together, and I promise you'll find the joy in unraveling the mysteries of chess data analysis. Stick with me until the end, and let's have some fun!

### Sample data

The open-source material used in this course can be accessed via one of the provided links below.

Link to the csv file: [Link](https://raw.githubusercontent.com/jihwankimdata/Power-Platform-For-Beginners/main/5-Power%20BI/chess_games.csv)

Here is the website [Link](https://www.mavenanalytics.io/data-playground) and the direct [download link](https://maven-datasets.s3.amazonaws.com/Online+Chess+Games/Online+Chess+Games.zip), from which the source data was acquired.

<br />
<br />

## <a name="chapter2"></a>2. Unlocking the power of Power BI: A Beginner's Guide 

In this comprehensive guide, I have meticulously structured a learning path for aspiring Power BI enthusiasts. I'll walk you through the foundational concepts, focusing solely on the essentials, while leveraging a sample dataset as a practical example. By the end of this course, you'll have crafted your very own Power BI report. Actively engage in the tutorial by downloading the dataset via the provided link.

Please note that the data model and the process outlined in this course represent one of many approaches to achieving the same results. Our goal here is to inject an element of enjoyment into your Power BI learning journey, especially if you're just starting out.

In this course, my chosen approach is to store the source data in Fabric Lakehouse. Nevertheless, if you have a different preference and wish not to house your source files or data within the Fabric Lakehouse environment, you have the option to effortlessly access the CSV file stored locally on your computer and seamlessly import it into Power BI Desktop. 
  

### What Is Power BI? 

Discover the capabilities of Power BI, an indispensable tool that empowers you to establish seamless connections with diverse data sources, transform data into compelling reports and dashboards, and effortlessly share insights with your chosen audience.

Unveiling Power BI's Key Components:

(1) Power BI Desktop: Your complimentary desktop companion, tailored for report creation and design.

(2) Power BI Service: The online hub for publishing, viewing, and distributing your reports and dashboards.

(3) Power BI Mobile Apps: Stay connected and informed while on the move, with easy access to your reports and dashboards.

Throughout this course, I will delve into the intricacies of configuring and connecting to the data source (Lakehouse). I'll guide you through the art of crafting and designing reports using Power BI Desktop. And, in a nutshell, I'll provide insights into sharing Power BI products via Power BI Service.

To harness the full potential of this course, make sure to register and obtain your Power BI Service credentials at <https://app.powerbi.com>. This will enable you to seamlessly transfer the CSV file from your local machine to Lakehouse, unleashing the power of data analysis at your fingertips.  
  

### What Is the Purpose of Power BI? 

Power BI belongs to the realm of Business Intelligence (BI) tools. The overarching goal of BI is to monitor Key Performance Indicators (KPIs) and unveil valuable insights within business data, enhancing decision-making processes throughout the entire organization.  

The utilization of Power BI varies according to individual roles, encompassing developers, analysts, managers, directors, and all other personnel within an organization. 
 

### Suggested Analyses by using the sample data:  

The contents of the analysis report are frequently communicated and presented to end-users in the form of a Proof of Concept (POC) version before commencing the development of the Power BI report.

As Power BI report developers, our responsibility entails sharing the following crucial aspects with end-users:

- The specific elements that users desire to be displayed in the report.
- The essential information that users need to access within the report.
- The valuable data and insights that users can derive from the report.

To achieve this, I will utilize sample data and assume that I have engaged in multiple conversations with users to establish a consensus on the report's contents, which include: 

(1) What is Black's optimal opening move that yields the highest probability of success following White's initial move of D4 (the data has 20,051 games information)? 

(2) What proportion of games were secured by the white player, and how many concluded as draws?  

(3) Which initial chess move was employed most frequently in games where black emerged victorious? Conversely, what was the prevalent opening move in games where white emerged as the winner?  

(4) What percentage of games were won by the participant with the superior rating? Is there any variance in this statistic based on the color of pieces?  

(5) Who is the user with the highest number of game wins? What percentage of these victories did the user achieve as the higher-rated player?

<br />
<br />

## <a name="chapter3"></a>3. Datamodel 
### Draw datamodel  

After engaging in conversations with key stakeholders and examining the column labels in the data source depicted in the figure below, the primary focus of our analysis will be to achieve the following objectives:

- Uncovering the outcomes of games, specifically discerning victories and defeats for the players.
- Pinpointing the specific moves within chess games that are associated with either a triumphant win or a regrettable loss.

![source column name](/5-Power%20BI/assets/source%20column%20name.jpg)


The data source can be neatly categorized into dimension tables, which provide detailed descriptions of the elements you wish to analyze, and fact tables that house the numerical data corresponding to the entities described within these dimensions. In the process of crafting our data model, the dimension tables are enriched with essential information about the Players and Games, while the fact table is enriched with intricate details about Moves.

The visualization of the data model is presented in the figure below. This data model serves as the foundation of our analytical framework. As a seasoned Power BI developer, I understand the importance of tailoring the data model to meet the specific requirements of the data source and the ever-evolving needs of our analytical reports.
I strongly advise that you begin by meticulously designing the data model before embarking on any data transformation. While it's natural for the data model's structure to evolve throughout the project, this initial blueprint serves as a guiding light, allowing developers to start their journey with confidence and precision.

![Datamodel planning fix](/5-Power%20BI/assets/Datamodel%20plan%20fix.jpg) 

 

### Store the source in Lakehouse  

The source is given as a CSV file. My approach involves saving this source data in a Fabric Lakehouse. And to refine and transform the data, I intend to employ Dataflow Gen2, although most of the transformations will occur in the Power Query Editor within Power BI Desktop. Finally, I'll reload the modified table back into the Lakehouse.

* Link to learn Fabric lakehouse: [Link](https://learn.microsoft.com/en-us/fabric/data-engineering/lakehouse-overview?wt.mc_id=DP-MVP-5004989)


(1) Create a workspace in app.powerbi.com

(2) Name the new workspace “PBI_For_Beginner”.

![Create Fabric workspace](/5-Power%20BI/assets/Create%20Fabric%20workspace.jpg)

<br />

(3) Create Lakehouse, and name it as “pbiforbeginner”.

![Create Lakehouse](/5-Power%20BI/assets/Create%20Lakehouse.jpg)

* Link to learn and explore the Microsoft Fabric Lakehouse: [Link](https://learn.microsoft.com/en-us/training/modules/get-started-lakehouses/2-fabric-lakehouse?wt.mc_id=DP-MVP-5004989)

<br />

(4) Upload the CSV file.

![Upload CSV to Lakehouse](/5-Power%20BI/assets/Upload%20CSV%20to%20Lakehouse.jpg)

<br />

(5) Now, the file is in the Lakehouse.  

(6) Load it to the table.

![Make CSV to Table in Lakehouse](/5-Power%20BI/assets/Make%20CSV%20to%20Table%20in%20Lakehouse.jpg)

<br />

(7) Once it is loaded, the source in the Lakehouse looks like below.  

![View a table in Lakehouse](/5-Power%20BI/assets/View%20a%20table%20in%20Lakehouse.jpg)

<br />

(8) Starting from the next step, the table within the Lakehouse will be utilized within Dataflow Gen2 to undergo transformation and be structured into a suitable dimension table and fact table. While this approach can be more practical in certain situations, this course will provide a brief demonstration of creating Dataflow Gen2 and loading it back into the Lakehouse. This aims to give you a basic understanding of Dataflow Gen2. However, it's important to note that the primary focus of this course will be on conducting the majority of transformations within Power BI Desktop's Power Query Editor.  

<br />

(9) Create Dataflow Gen2.

![Create Dataflow Gen2](/5-Power%20BI/assets/Create%20Dataflow%20Gen2.jpg)

* Link to learn and understand Dataflow Gen2 in Microsoft Fabric: [Link](https://learn.microsoft.com/en-us/training/modules/use-dataflow-gen-2-fabric/2-dataflows-gen-2?wt.mc_id=DP-MVP-5004989)

<br />

(10) Connect to Lakehouse (pbiforbeginner).

![Connect to Lakehouse](/5-Power%20BI/assets/Dataflow%20Gen2%20connect%20to%20Lakehouse%20step%201.jpg)

![Connect to Lakehouse](/5-Power%20BI/assets/Dataflow%20Gen2%20connect%20to%20Lakehouse%20step%202.jpg)

<br />

(11) Rename Dataflow Gen2 as “Chess_Games” and publish it later to save it up to this step.

![Dataflow Gen2 save](/5-Power%20BI/assets/Dataflow%20Gen2%20save.jpg)



<span style="color:green">*Note: From this step, it is to load data back to Lakehouse, import it into Power BI Desktop, transform data in the Power Query Editor, load it to Power BI and create a datamodel in Power BI.*</span> 

<br />

(12) Select Data destination as Lakehouse. 

![Dataflow Gen2 destination](/5-Power%20BI/assets/Dataflow%20Gen2%20destination.jpg)

![Dataflow Gen2 destination lakehouse](/5-Power%20BI/assets/Dataflow%20Gen2%20dest%20lakehouse.jpg)

![Dataflow Gen2 dest tablename](/5-Power%20BI/assets/Dataflow%20Gen2%20dest%20tablename.jpg)

![Dataflow Gen2 dest replace](/5-Power%20BI/assets/Dataflow%20Gen2%20dest%20replace.jpg)

![Dataflow Gen2 publish](/5-Power%20BI/assets/Dataflow%20Gen2%20publish.jpg)

<br />

(13) Once the loading of “Chess_Games” Dataflow Gen2 is done, go to “pbiforbeginner” Lakehouse to check whether the “chess_games_source” is added.

![Lakehouse contains new table from Dataflow Gen2](/5-Power%20BI/assets/Lakehouse%20contains%20new%20table%20from%20dataflow%20gen2.jpg)

<br />

(14) This table is identical to the "chess_games" table located above within the same folder. The procedures executed in Dataflow Gen2 are not required in this scenario. Nevertheless, it's worth noting that if you perform additional table transformation steps in Dataflow Gen2, the outcome will vary. For this course, I have chosen to conduct further table transformation steps later within Power BI Desktop's Power Query Editor. 

<br />
<br />

## <a name="chapter4"></a>4. Open Power BI Desktop 

(1) To use Power BI Desktop and connect to the pbiforbeginner Lakehouse, make sure you're using the same login ID that was used when the Lakehouse was created.

![pbi desktop connect to lakehouse](/5-Power%20BI/assets/pbi%20desktop%20connect%20to%20lakehouse.jpg)


![lakehouse select](/5-Power%20BI/assets/lakehouse%20select.jpg)

![lakehouse table import](/5-Power%20BI/assets/lakehouse%20table%20import.jpg)

<span style="color:green">*Note: If you prefer not to connect to the Lakehouse and instead wish to import the CSV file directly from your local computer, please follow the steps outlined below. It's important to be aware that local files may not always automatically assign column titles. In such instances, you can manually assign column titles within the Power Query Editor.*</span>

![import csv file](/5-Power%20BI/assets/PBI%20Desktop%20connect%20to%20CSV%20file.jpg)
![use first row as headers](/5-Power%20BI/assets/PQEditor%20use%20first%20row%20as%20headers.jpg)

<br />

(2) The "chess_games_source" table is imported into Power Query Editor. Since this table serves as the source for dimension tables and a fact table, which will be loaded into the Power BI report to construct a data model, the [Enable load] option is unchecked (equivalent to disabling load). Instead, we will create dimension tables and a fact table by referencing this source table.

<span style="color:green">*Note: In Power Query Editor within Power BI, the fundamental distinction between "Copy" and "Reference" tables lies in their behavior when creating a new table. When you "Copy" a table, it duplicates the entire table's data, resulting in a completely separate table with its own set of data. This means that any changes made to the copied table will not affect the original. On the other hand, when you "Reference" a table, you create a new table that simply points back to the original data source. This means that the referenced table shares the same data as the source, and any transformations or modifications applied to the source will automatically reflect in the referenced table. "Reference" tables are useful when you want to work with the same data in different ways without duplicating it, maintaining data consistency across multiple queries.*</span>

![pq editor disable load](/5-Power%20BI/assets/pq%20editor%20disable%20load.jpg)

* Link to learn Referencing Power Query queries: [Link](https://learn.microsoft.com/en-us/power-bi/guidance/power-query-referenced-queries?wt.mc_id=DP-MVP-5004989)

<br />

(3) Create dim_player table. 

![pq editor dim table](/5-Power%20BI/assets/pq%20editor%20dim%20table.jpg)

<br />

(4) Proceed with the transformation steps outlined in the query. For a more detailed description of the M codes used, please refer to the "Advanced Editor." In summary, the purpose of this transformation is as follows:

- Retrieve the black id column and the white id column.
- Merge these two columns into a single column named "player_id."
- Introduce an index column to assign identification numbers.

![pq editor dim table final](/5-Power%20BI/assets/pq%20editor%20dim%20table%20final.jpg)


![dim table advanced editor](/5-Power%20BI/assets/pq%20editor%20dim%20table%20advanced%20editor.jpg)

<span style="color:green">*Note: The following M code, complete with explanatory comments denoted by "//," outlines the step-by-step thought process behind code selection and composition. Feel assured that, despite the potential complexity of the M code within the Advanced Editor, there's no need to be intimidated. You can readily copy and paste the entire M code into Power Query Editor's Advanced Editor. While some of the M code in this course may appear intricate, don't hesitate to rely on the embedded comments to gain insight into my thought process and the M functions I considered using to achieve the desired outcome for each query*</span>

```M
let
    Source = chess_games_source,

    // only select white id column

    #"white id" = Table.SelectColumns(Source,{"white_id"}),
    #"rename it to player id (white)" = Table.RenameColumns(#"white id",{{"white_id", "player_id"}}),

    // only select black id column from the source, not from the previous step

    #"black id" = Table.SelectColumns(Source,{"black_id"}),
    #"rename it to palyer id (black)" = Table.RenameColumns(#"black id",{{"black_id", "player_id"}}),

    // append the white id column and black id column

    #"Appended Query" = Table.Combine({#"rename it to player id (white)", #"rename it to palyer id (black)"}),

    // remove duplicated ids

    #"Removed Duplicates" = Table.Distinct(#"Appended Query"),
    #"Sorted Rows" = Table.Sort(#"Removed Duplicates",{{"player_id", Order.Ascending}}),

    // create index column as primary key column

    #"Added Index" = Table.AddIndexColumn(#"Sorted Rows", "player_id_index", 1, 1, Int64.Type)
in
    #"Added Index"
```
* Link to learn Table.SelectColumns M code: [Link](https://learn.microsoft.com/en-us/powerquery-m/table-selectcolumns?wt.mc_id=DP-MVP-5004989)
* Link to learn Table.Combine M code: [Link](https://learn.microsoft.com/en-us/powerquery-m/table-combine?wt.mc_id=DP-MVP-5004989)
* Link to learn Table.Distinct M code: [Link](https://learn.microsoft.com/en-us/powerquery-m/table-distinct?wt.mc_id=DP-MVP-5004989)
* Link to learn Table.Sort M code: [Link](https://learn.microsoft.com/en-us/powerquery-m/table-sort?wt.mc_id=DP-MVP-5004989)
* Link to learn Table.AddIndexColumn M code: [Link](https://learn.microsoft.com/en-us/powerquery-m/table-addindexcolumn?wt.mc_id=DP-MVP-5004989)

<br />

(5) Reference the source table and create dim_game table.

![pq editor dim table](/5-Power%20BI/assets/pq%20editor%20dim%20table%20table.jpg)

<br />

(6) Follow the transformation steps. The M codes are comprehensively explained within the "Advanced Editor." The purpose of this transformation is outlined as follows:
- Eliminate extraneous columns, such as the moves column, which is designed for the fact table, rather than the dimension table.
- Substitute the white_id and black_id columns in this table with white_player_id_index and black_player_id_index for enhanced clarity.

![advanced editor](/5-Power%20BI/assets/pq%20editor%20dim%20tabletable%20advaned%20editor.jpg)

 
```M
let
    Source = chess_games_source,

    // remove unneccessary columns

    #"Removed Other Columns" = Table.SelectColumns(Source,{"game_id", "rated", "turns", "victory_status", "winner", "time_increment", "white_id", "white_rating", "black_id", "black_rating", "opening_fullname", "opening_shortname"}),

    // use player_id_index column from dim_player table for creating a foreign key column for white players and black players

    #"Merged Queries" = Table.NestedJoin(#"Removed Other Columns", {"white_id"}, dim_player, {"player_id"}, "dim_player", JoinKind.LeftOuter),
    #"Expanded dim_player" = Table.ExpandTableColumn(#"Merged Queries", "dim_player", {"player_id_index"}, {"player_id_index"}),
    #"Renamed Columns" = Table.RenameColumns(#"Expanded dim_player",{{"player_id_index", "white_player_id_index"}}),
    #"Merged Queries1" = Table.NestedJoin(#"Renamed Columns", {"black_id"}, dim_player, {"player_id"}, "dim_player", JoinKind.LeftOuter),
    #"Expanded dim_player1" = Table.ExpandTableColumn(#"Merged Queries1", "dim_player", {"player_id_index"}, {"player_id_index"}),
    #"Renamed Columns1" = Table.RenameColumns(#"Expanded dim_player1",{{"player_id_index", "black_player_id_index"}}),
    
    #"Removed Other Columns1" = Table.SelectColumns(#"Renamed Columns1",{"game_id", "rated", "turns", "victory_status", "winner", "time_increment", "white_rating", "black_rating", "opening_fullname", "opening_shortname", "white_player_id_index", "black_player_id_index"})
in
    #"Removed Other Columns1" 
```
* Link to learn Table.SelectColumns M code: [Link](https://learn.microsoft.com/en-us/powerquery-m/table-selectcolumns?wt.mc_id=DP-MVP-5004989)
* Link to learn Table.NestedJoin M code: [Link](https://learn.microsoft.com/en-us/powerquery-m/table-nestedjoin?wt.mc_id=DP-MVP-5004989)
* Link to learn Table.RenameColumns M code: [Link](https://learn.microsoft.com/en-us/powerquery-m/table-renamecolumns?wt.mc_id=DP-MVP-5004989)

<span style="color:green">*Note: Combining two columns from separate tables (Merge operation) and extracting the desired column can be easily accomplished through the user-friendly interface by following the steps below.*</span>

![power query merge ui](/5-Power%20BI/assets/power%20query%20merge%20UI.jpg)
![pwer query expand column](/5-Power%20BI/assets/power%20query%20expand%20column.jpg)

<br />

(7) Reference the source table and create moves_fct table. 

<br />

(8) Follow the transformation steps. Detailed descriptions of the M codes can be found in the "Advanced Editor." The primary objective of this transformation is as follows:
- Select a column containing all moves per game and split them into individual rows within the same game_id.
- Assign a sequential numbering to each move within each game_id.

![pq editor fct table](/5-Power%20BI/assets/pq%20editor%20fct%20table.jpg)
![pq editor fct table](/5-Power%20BI/assets/pq%20editor%20fct%20table%20advanced%20editor.jpg)

 
```M
let
    Source = chess_games_source,

    // remove unneccessary columns

    #"Removed Other Columns" = Table.SelectColumns(Source,{"game_id", "moves"}),

    // the moves column contains all moves with spaces that differenciate each move, so split it by space
    // split it vertically by game id

    #"Split Column by Delimiter" = Table.ExpandListColumn(Table.TransformColumns(#"Removed Other Columns", {{"moves", Splitter.SplitTextByDelimiter(" ", QuoteStyle.Csv), let itemType = (type nullable text) meta [Serialized.Text = true] in type {itemType}}}), "moves"),

    // create move number column in each game
    // group by each game id and add index column as a move number column

    #"Grouped Rows" = Table.Group(#"Split Column by Delimiter", {"game_id"}, {{"moves", each Table.AddIndexColumn( _, "move_number", 1, 1, Int64.Type)}}),
    #"Expanded moves" = Table.ExpandTableColumn(#"Grouped Rows", "moves", {"moves", "move_number"}, {"moves", "move_number"}),
    #"Changed Type" = Table.TransformColumnTypes(#"Expanded moves",{{"moves", type text}, {"move_number", Int64.Type}})
in
    #"Changed Type"
```
* Link to learn Table.ExpandListColumn M code: [Link](https://learn.microsoft.com/en-us/powerquery-m/table-expandlistcolumn?wt.mc_id=DP-MVP-5004989)
* Link to learn Table.Group M code: [Link](https://learn.microsoft.com/en-us/powerquery-m/table-group?wt.mc_id=DP-MVP-5004989)
* Link to learn Table.TransformColumnTypes M code: [Link](https://learn.microsoft.com/nl-nl/powerquery-m/table-transformcolumntypes?wt.mc_id=DP-MVP-5004989)


<span style="color:green">*Note: Splitting a column into rows can be effortlessly accomplished using the Power Query Editor's user-friendly interface. After selecting the column you wish to split into rows, simply follow the steps below.*</span>

![pq split into row](/5-Power%20BI/assets/power%20query%20split%20into%20row.jpg)

<br />

(9) Close and apply to Power BI Desktop 

![load from pq to pbi](/5-Power%20BI/assets/load%20tables%20from%20pq%20to%20pbi.jpg)

<br />

(10) Establish Table Relationships. Aligning with the Data Model Blueprint Presented at the Course Onset  

<br />

(11) Navigate to the Model View, and seamlessly link columns by dragging one from one table and connecting it to another from a separate table. 

- dim_player[player_id_index] to dim_game[white_player_id_index]
- dim_player[player_id_index] to dim_game[black_player_id_index]
- dim_game[game_id] to moves_fct[game_id]
- An inactive relationship is depicted as a dotted line, and it can be activated by implementing an appropriate DAX function, such as the "USERELATIONSHIP" DAX function, when the need arises. To access detailed information about each relationship, you can click on "Manage relationships."

![datamodel view](/5-Power%20BI/assets/datamodel%20view.jpg)

![relationship manage view in pbi](/5-Power%20BI/assets/relationship%20manage%20view.jpg)


<br />
<br />

## <a name="chapter5"></a>5. DAX measures and Visualizations (Proof Of Concept) 

### Create DAX measures and visualizations to validate data. 

Before commencing this session, it is advisable to review and comprehend two Microsoft links that offer valuable insights.

Learn concept of DAX by video Link: [Link](https://learn.microsoft.com/en-us/dax/dax-learn-videos?wt.mc_id=DP-MVP-5004989) 

DAX Glossaries Link: [Link](https://learn.microsoft.com/en-us/dax/dax-glossary?wt.mc_id=DP-MVP-5004989)
 

(1) Prior to embarking on the development of visualizations and DAX measures, it is imperative to grasp the fundamentals of DAX (Data Analysis Expressions). The two Microsoft links provided above offer valuable resources for initiating your understanding of DAX concepts. 

(2) As mentioned earlier in this document, I previously discussed the topics of conversation with the stakeholders who will be reviewing this report. In our discussions, we explored five key subjects, which I would like to reiterate below, arranged in order of the ease and effectiveness with which insights can be derived first. 

- What proportion of games were secured by the white player, and how many concluded as draws? 
- Which initial chess move was employed most frequently in games where black emerged victorious? Conversely, what was the prevalent opening move in games where white emerged as the winner?
- Who is the user with the highest number of game wins? What percentage of these victories did the user achieve as the higher-rated player?
- What percentage of games were won by the participant with the superior rating? Is there any variance in this statistic based on the color of pieces?
- What is the initial move for Black that demonstrates the highest likelihood of winning after White's first move of D4?

<span style="color:green">*Note: During this session, we shall craft DAX measures and visualizations with the primary purpose of scrutinizing and substantiating data integrity, addressing pertinent inquiries, and validating responses. This phase constitutes an integral component of the initial proof of concept (POC) iteration. Subsequently, a Power BI report tailored for production will be meticulously conceived and developed, building upon the foundations laid during this preliminary POC phase, with the ultimate aim of sharing it effectively with stakeholders.*</span>


(3) Let's proceed to generate visualizations and DAX measures in response to the aforementioned request. To streamline the first request, our objective is to determine the total number of games won, lost, or drawn by both white and black players.

(4) To systematically consolidate DAX measures, I establish a blank table and designate it as "Key_Measures." This table will exclusively house DAX measures for improved organization and clarity.

![create measure table](/5-Power%20BI/assets/create%20measure%20table.jpg)
 
<br />

(5) On the empty canvas, add a table visualization and then drag the [winner] column from the dim_game table. Please note that the ultimate visualization may not remain a table; nevertheless, this step assists in visualizing and comprehending the required information that needs to be presented and crafted in the final visualization. 

<br />

(6) Create a DAX measure to tally wins by black, white, or draws. Currently, the order in the table visualization is alphabetical, displaying "Black," "Draw," and then "White." To correct this order and have it displayed as "White," "Black," and "Draw," we need to generate a new column within the same table using Power Query Editor. This new column will assign values such as White = 1, Black = 2, and Draw = 3. Subsequently, we can sort the [winner] column based on the newly created column. In Power Query Editor, you can create a new column by adding a step through the "fx" button in the formula bar or by incorporating M code within the Advanced Editor.

![analysis01](/5-Power%20BI/assets/analysis01.jpg)
![analysis01pwerqueryeditor](/5-Power%20BI/assets/analysis01PQeditor.jpg) 
![analysis01powerqueryadvancededitor](/5-Power%20BI/assets/analysis01pqadvancededitor.jpg)

```M
let 

    Source = chess_games_source,   

    // remove unneccessary columns 

    #"Removed Other Columns" = Table.SelectColumns(Source,{"game_id", "rated", "turns", "victory_status", "winner", "time_increment", "white_id", "white_rating", "black_id", "black_rating", "opening_fullname", "opening_shortname"}),   

    // use player_id_index column from dim_player table for creating a foreign key column for white players and black players 

    #"Merged Queries" = Table.NestedJoin(#"Removed Other Columns", {"white_id"}, dim_player, {"player_id"}, "dim_player", JoinKind.LeftOuter), 

    #"Expanded dim_player" = Table.ExpandTableColumn(#"Merged Queries", "dim_player", {"player_id_index"}, {"player_id_index"}), 

    #"Renamed Columns" = Table.RenameColumns(#"Expanded dim_player",{{"player_id_index", "white_player_id_index"}}), 

    #"Merged Queries1" = Table.NestedJoin(#"Renamed Columns", {"black_id"}, dim_player, {"player_id"}, "dim_player", JoinKind.LeftOuter), 

    #"Expanded dim_player1" = Table.ExpandTableColumn(#"Merged Queries1", "dim_player", {"player_id_index"}, {"player_id_index"}), 

    #"Renamed Columns1" = Table.RenameColumns(#"Expanded dim_player1",{{"player_id_index", "black_player_id_index"}}),      

    #"Removed Other Columns1" = Table.SelectColumns(#"Renamed Columns1",{"game_id", "rated", "turns", "victory_status", "winner", "time_increment", "white_rating", "black_rating", "opening_fullname", "opening_shortname", "white_player_id_index", "black_player_id_index"}),      

    #"Add winner sort order column" = Table.AddColumn(#"Removed Other Columns1",  

   "winner sort order", each if [winner] = "White" then 1 else  

   if [winner] = "Black" then 2 else  

   if [winner] = "Draw" then 3 else  

   "check again", Int64.Type) 

in 

    #"Add winner sort order column" 
```
* Link to learn Table.AddColumn M code: [Link](https://learn.microsoft.com/nl-nl/powerquery-m/table-addcolumn?wt.mc_id=DP-MVP-5004989)

<br />

(7) Close and apply Power Query Editor and configure sort order.

![sort column](/5-Power%20BI/assets/sort%20column.jpg) 

<br />

(8) Create DAX measure. My approach to crafting a DAX measure to address this inquiry involves the following steps:
- Extract the relevant column from the 'dim_game' table that can provide a summary based on 'white winner,' 'black winner,' and 'draw'.
- For each of these winner categories, calculate a distinct count of the game IDs within that respective category.


    As described in the below, the answer to the first request is,  

- Total 20,058 games 
- White wins 10,001 games 
- Black wins 9,107 games 
- Draw happens in 950 games 

![analysis 01 result](/5-Power%20BI/assets/analysis01result.jpg)

The DAX measure utilized on this page is composed as follows.

```dax
Win count = 
    DISTINCTCOUNT(dim_game[game_id])
```
* Link to learn DISTINCTCOUNT DAX function: [Link](https://learn.microsoft.com/en-us/dax/distinctcount-function-dax?wt.mc_id=DP-MVP-5004989)

<br />

(9) The second request can be rephrased as follows: "What is the first move most commonly played in games won by black and games won by white?" To address this question, the following DAX measures have been developed and are employed in the New Card visualization. The "The most winning first move by white" DAX measure includes comments within the formula to clarify the significance of each variable. In addition, the comments within the DAX measure also serve to elucidate the thought process I underwent while creating the measure. All other measures that are used in this Power BI page are written in a very similar way with [The most winning first move by white] DAX measure. Please do not be misled by the fact that black players' first move is consistently recorded as move_number = 2. In response to the second request, the findings are as follows:

- The move e4 stands out as the most frequently played winning first move by white players.
- The move e5 emerges as the most commonly played winning first move by black players.
- White players secure victory in 6371 games when their first move is e4.
- Black players achieve victory in 3101 games when their first move is e5.

![analysis02](/5-Power%20BI/assets/analysis02.jpg)

The DAX measures utilized on this page is composed as follows.

```dax
The most winning first move by white = 

VAR _whitewintable =  //Generate a virtual table that displays the initial moves of white players who have won their games.
    FILTER (
        SUMMARIZE (
            FILTER ( moves_fct, moves_fct[move_number] = 1 ),
            moves_fct[moves],
            dim_game[game_id],
            dim_game[winner]
        ),
        dim_game[winner] = "White"
    )

VAR _countfirstmove =   // Group the initial moves in the table above while also adding a count column. 
    GROUPBY (
        _whitewintable,
        moves_fct[moves],
        "@count", SUMX ( CURRENTGROUP (), 1 )
    )

VAR _maxwin =   // The highest count number indicates the most frequently played initial move.
    MAXX ( _countfirstmove, [@count] )

VAR _mostwinningfirstmove =
    FILTER ( _countfirstmove, [@count] = _maxwin )
    
RETURN
    CONCATENATEX ( _mostwinningfirstmove, moves_fct[moves], ", " )
```
* Link to learn FILTER DAX function: [Link](https://learn.microsoft.com/en-us/dax/filter-function-dax?wt.mc_id=DP-MVP-5004989)
* Link to learn SUMMARIZE DAX function: [Link](https://learn.microsoft.com/en-us/dax/summarize-function-dax?wt.mc_id=DP-MVP-5004989)
* Link to learn GROUPBY DAX function: [Link](https://learn.microsoft.com/en-us/dax/groupby-function-dax?wt.mc_id=DP-MVP-5004989)
* Link to learn MAXX DAX function: [Link](https://learn.microsoft.com/en-us/dax/maxx-function-dax?wt.mc_id=DP-MVP-5004989>)
* Link to learn CONCATENATEX DAX function: [Link](https://learn.microsoft.com/en-us/dax/concatenatex-function-dax?wt.mc_id=DP-MVP-5004989)


```dax
The most winning first move by black = 

VAR _blackwintable =    // The first move for black players is always the second move in the game.
    FILTER (
        SUMMARIZE (
            FILTER ( moves_fct, moves_fct[move_number] = 2 ),
            moves_fct[moves],
            dim_game[game_id],
            dim_game[winner]
        ),
        dim_game[winner] = "Black"
    )
VAR _countfirstmove =
    GROUPBY (
        _blackwintable,
        moves_fct[moves],
        "@count", SUMX ( CURRENTGROUP (), 1 )
    )
VAR _maxwin =
    MAXX ( _countfirstmove, [@count] )
VAR _mostwinningfirstmove =
    FILTER ( _countfirstmove, [@count] = _maxwin )
RETURN
    CONCATENATEX ( _mostwinningfirstmove, moves_fct[moves], ", " )
```

```dax
How many wins by this first move by white =

VAR _whitewintable =
    FILTER (
        SUMMARIZE (
            FILTER ( moves_fct, moves_fct[move_number] = 1 ),
            moves_fct[moves],
            dim_game[game_id],
            dim_game[winner]
        ),
        dim_game[winner] = "White"
    )
VAR _countfirstmove =
    GROUPBY (
        _whitewintable,
        moves_fct[moves],
        "@count", SUMX ( CURRENTGROUP (), 1 )
    )
VAR _maxwin =
    MAXX ( _countfirstmove, [@count] )
RETURN
    _maxwin
```

```dax
How many wins by this first move by black = 

VAR _blackwintable =
    FILTER (
        SUMMARIZE (
            FILTER ( moves_fct, moves_fct[move_number] = 2 ),
            moves_fct[moves],
            dim_game[game_id],
            dim_game[winner]
        ),
        dim_game[winner] = "Black"
    )
VAR _countfirstmove =
    GROUPBY (
        _blackwintable,
        moves_fct[moves],
        "@count", SUMX ( CURRENTGROUP (), 1 )
    )
VAR _maxwin =
    MAXX ( _countfirstmove, [@count] )
RETURN
    _maxwin
```

<br />

<span style="color:green">*Note: In this course, some of the DAX measures may pose a slight challenge for beginners in terms of both writing and comprehension. However, the insights shared here on how to initiate the process of creating DAX measures, along with the comments provided within the DAX measures to explain the rationale behind using specific DAX functions, are instrumental in guiding your thought process when crafting your own DAX measures. While mastering DAX functions is crucial, it is equally vital to learn how to analyze problem statements and determine the appropriate DAX functions to effectively address these problem statements.*</span>

<br />

(10) The third request, rephrased for clarity, is to identify the player with the most wins and calculate their winning percentage against opponents with a higher rating. The thought process for developing a solution entails the following steps:
- Extract the 'player_id' column from the 'dim_player' table.
- Calculate the counts of game IDs corresponding to 'white-win' and 'black-win' outcomes. Take into account the inactive relationship when calculating 'black-win.'
- In the creation of virtual tables for 'white-win' and 'black-win' within a DAX measure, I could apply filters to only include matches against higher-rated opponents for a more precise analysis.

    After creating a table visualization like below with DAX measures, when clicking the three dots located in the upper right side of the table visualization, you can sort by any DAX measure that is used in the visualization. Or you can simply click the measure name itself in the visualization. The answer to this question is, 

- Player id = taranga wins 72 games. 
- And out of the 72 games played, 36 were won against higher-rated opponents (50%). 

![analysis03](/5-Power%20BI/assets/analysis03.jpg)

The DAX measures utilized on this page is composed as follows.

```dax
Winning count by player = 

VAR _whiteplay =
    COUNTROWS ( FILTER ( dim_game, dim_game[winner] = "White" ) )

// Use the USERELATIONSHIP DAX function to activate an inactive relationship in the data model.    
VAR _blackplay =    
    CALCULATE (
        COUNTROWS ( FILTER ( dim_game, dim_game[winner] = "Black" ) ),
        USERELATIONSHIP ( dim_player[player_id_index], dim_game[black_player_id_index] )
    )
    
RETURN
    _whiteplay + _blackplay
```
* Link to learn COUNTROWS DAX function: [Link](https://learn.microsoft.com/en-us/dax/countrows-function-dax?wt.mc_id=DP-MVP-5004989)
* Link to learn USERELATIONSHIP DAX function: [Link](https://learn.microsoft.com/en-us/dax/userelationship-function-dax?wt.mc_id=DP-MVP-5004989)
* Link to learn CALCULATE DAX function: [Link](https://learn.microsoft.com/en-us/dax/calculate-function-dax?wt.mc_id=DP-MVP-5004989)


```dax
Win count when oponent is higher rated = 

VAR _wincountbywhite =
    COUNTROWS (
        FILTER (
            dim_game,
            dim_game[winner] = "White"
                && dim_game[white_rating] < dim_game[black_rating]
        )
    )

// Use the USERELATIONSHIP DAX function to activate an inactive relationship in the data model.    
VAR _wincountbyblack =    
    CALCULATE (
        COUNTROWS (
            FILTER (
                dim_game,
                dim_game[winner] = "Black"
                    && dim_game[black_rating] < dim_game[white_rating]
            )
        ),
        USERELATIONSHIP ( dim_player[player_id_index], dim_game[black_player_id_index] )
    )
    
RETURN
    _wincountbywhite + _wincountbyblack
```

```dax
Winning higher rated player percentage = 
    DIVIDE( [Win count when oponent is higher rated], [Winning count by player] )
``` 
* Link to learn DIVIDE DAX function: [Link](https://learn.microsoft.com/en-us/dax/divide-function-dax?wt.mc_id=DP-MVP-5004989)

<br />

(11) The fourth request involves calculating the percentage of wins by higher-rated players, which amounts to 61.58%. This information can be presented through both a table visualization and a card visualization, as demonstrated below:

![analysis04 table visualization](/5-Power%20BI/assets/analysis04tablevisual.jpg)
![analysis04 card visualization](/5-Power%20BI/assets/analysis04cardvisual.jpg)

The DAX measures utilized on this page is composed as follows.

```dax
White higher rated win count = 

COUNTROWS (
    FILTER (
        dim_game,
        dim_game[white_rating] > dim_game[black_rating]
    )
)
```

```dax
Black higher rated win count = 

COUNTROWS (
    FILTER (
        dim_game,
        dim_game[white_rating] < dim_game[black_rating]
    )
)
```

```dax
Win by higher rated players ratio = 

VAR _whitewin =
    COUNTROWS (
        FILTER (
            dim_game,
            dim_game[winner] = "White"
                && dim_game[white_rating] > dim_game[black_rating]
        )
    )
VAR _blackwin =
    COUNTROWS (
        FILTER (
            dim_game,
            dim_game[winner] = "Black"
                && dim_game[white_rating] < dim_game[black_rating]
        )
    )
VAR _allgamescount =
    COUNTROWS ( dim_game )
RETURN
    DIVIDE ( _whitewin + _blackwin, _allgamescount )
``` 

<br />

(12) The final question, expressed in a more straightforward manner, is, after White plays the first move D4, what is the most advantageous opening move for Black in terms of achieving the highest winning percentage? The thought process unfolds as follows, facilitating the creation of a more intuitive DAX measure:
- Commence by filtering the 'moves_fct' table to include only instances where the first move is 'D4.
- Utilize this criterion to identify games that were won by Black from the dim_game table.
- To the resulting table, introduce a new column that calculates the move number as 2.
- Group the table by move number = 2 and calculate the count of games.
- Determine the highest count number among these counts.
- Identify the move that corresponds to the highest count number, as it shares the same count value as the highest count number.

![analysis05](/5-Power%20BI/assets/analysis05.jpg)

The DAX measures utilized on this page is composed as follows.

```dax
Black most winning move after white first move d4 = 

VAR _blackwinafterDfour =
    FILTER (
        SUMMARIZE (
            FILTER ( moves_fct, moves_fct[move_number] = 1 && moves_fct[moves] = "d4" ),
            dim_game[game_id],
            dim_game[winner]
        ),
        dim_game[winner] = "Black"
    )

VAR _addblackfirstmove =
    ADDCOLUMNS (
        _blackwinafterDfour,
        "@blackfirstmove",
            CALCULATE (
                MAXX ( FILTER ( moves_fct, moves_fct[move_number] = 2 ), moves_fct[moves] )
            )
    )

VAR _groupbyblackfirstmovecount =
    GROUPBY (
        _addblackfirstmove,
        [@blackfirstmove],
        "@count", SUMX ( CURRENTGROUP (), 1 )
    )

VAR _maxcount =
    MAXX ( _groupbyblackfirstmovecount, [@count] )

RETURN
    MAXX (
        FILTER ( _groupbyblackfirstmovecount, [@count] = _maxcount ),
        [@blackfirstmove]
    )
```
* Link to learn ADDCOLUMNS DAX function: [Link](https://learn.microsoft.com/en-us/dax/addcolumns-function-dax?wt.mc_id=DP-MVP-5004989)

<br />

(13) Until this juncture, I have developed DAX measures and visualizations within the Power BI Desktop file, serving as a proof of concept (POC) version. Moving forward, my focus shifts to crafting charts imbued with purposeful colors, thereby rendering a more intuitive and insightful experience.

<br />
<br />

## <a name="chapter6"></a>6. DAX measures and Visualizations (Production) 

### Create DAX measures & visualizations, and design Power BI report to provide insights.

In the previous session, I diligently verified the functionality of the data model to ensure its accuracy in displaying the relevant information. In this current session, I am poised to elevate the presentation of valuable insights by employing various visualization techniques. These include not only the table and card visualizations but also more dynamic and informative options such as bar charts, column charts, and others.

The line chart, while typically a powerful tool for illustrating trends over time, may not be suitable for this report due to the absence of date/time dimensions in the dataset.

(1) The first objective is to ascertain the cumulative number of games won, lost, or drawn by both white and black players. To convey this information in a more intuitive manner, I have opted to employ a bar chart. To enhance the clarity of this visualization, I have incorporated the win count and percentage within labels attached to each bar. This is accomplished through the utilization of the Custom Label feature, complemented by the creation of DAX measures as outlined below:

![win count by winner bar chart](/5-Power%20BI/assets/Win%20count%20by%20winner%20bar%20chart.jpg)

The additinoal DAX measures utilized on this page is composed as follows.

```dax
Win count percentage = 
VAR _allgames =
    CALCULATE (
        [Win count],
        REMOVEFILTERS ( dim_game[winner], dim_game[winner sort order] )
    )
VAR _wincount = [Win count]
RETURN
    DIVIDE ( _wincount, _allgames )
```
* Link to learn REMOVEFILTERS DAX function: [Link](https://learn.microsoft.com/en-us/dax/removefilters-function-dax?wt.mc_id=DP-MVP-5004989)

```dax
Win count by winner label = 
FORMAT ( [Win count], "#,#0" ) & " | "
    & FORMAT ( [Win count percentage], "#0.00%" )
```
* Link to learn FORMAT DAX function: [Link](https://learn.microsoft.com/en-us/dax/format-function-dax?wt.mc_id=DP-MVP-5004989)

<br />

(2) The second inquiry pertains to identifying the most frequently employed first moves in games that were victorious for both black and white players. To present this information effectively, I have opted for a table visualization as the most suitable medium. To achieve this, it is imperative to include the [winner] column from the dim_game table in the table visualization. To facilitate this integration, I have slightly adjusted the formulation of the DAX measures, as detailed below:

![most winning first move](/5-Power%20BI/assets/most%20winning%20first%20move.jpg)

The additinoal DAX measures utilized on this page is composed as follows.

```dax
The most winning first move = 
VAR _whitewintable =
    //Generate a virtual table displaying the initial move in each victorious game.
    SUMMARIZE (
        FILTER ( moves_fct, moves_fct[move_number] = 1 ),
        moves_fct[moves],
        dim_game[game_id]
    )
VAR _whitecountfirstmove =
    // Group the initial moves in the table above and add an extra column to count each move. 
    GROUPBY (
        _whitewintable,
        moves_fct[moves],
        "@count", SUMX ( CURRENTGROUP (), 1 )
    )
VAR _whitemaxwin =
    // The 'Maximum Counting Number' represents the most frequently played initial move.
    MAXX (
        _whitecountfirstmove,
        [@count]
    )
VAR _whitemostwinningfirstmove =
    FILTER ( _whitecountfirstmove, [@count] = _whitemaxwin )
VAR _blackwintable =
    SUMMARIZE (
        FILTER ( moves_fct, moves_fct[move_number] = 2 ),
        moves_fct[moves],
        dim_game[game_id]
    )
VAR _blackcountfirstmove =
    GROUPBY (
        _blackwintable,
        moves_fct[moves],
        "@count", SUMX ( CURRENTGROUP (), 1 )
    )
VAR _blackmaxwin =
    MAXX ( _blackcountfirstmove, [@count] )
VAR _blackmostwinningfirstmove =
    FILTER ( _blackcountfirstmove, [@count] = _blackmaxwin )
RETURN
    SWITCH (
        SELECTEDVALUE ( dim_game[winner] ),
        "White", CONCATENATEX ( _whitemostwinningfirstmove, moves_fct[moves], ", " ),
        "Black", CONCATENATEX ( _blackmostwinningfirstmove, moves_fct[moves], ", " )
    )
```
* Link to learn SWITCH DAX function: [Link](https://learn.microsoft.com/en-us/dax/switch-function-dax?wt.mc_id=DP-MVP-5004989)
* Link to learn SELECTEDVALUE DAX function: [Link](https://learn.microsoft.com/en-us/dax/selectedvalue-function?wt.mc_id=DP-MVP-5004989)

```dax
How many wins by this first move = 
VAR _whitewintable =
    //Generate a virtual table displaying the initial move in each victorious game.
    SUMMARIZE (
        FILTER ( moves_fct, moves_fct[move_number] = 1 ),
        moves_fct[moves],
        dim_game[game_id]
    )
VAR _whitecountfirstmove =
    // Group the initial moves in the table above and add an extra column to count each move. 
    GROUPBY (
        _whitewintable,
        moves_fct[moves],
        "@count", SUMX ( CURRENTGROUP (), 1 )
    )
VAR _whitemaxwin =
    // The 'Maximum Counting Number' represents the most frequently played initial move.
    MAXX (
        _whitecountfirstmove,
        [@count]
    )
VAR _blackwintable =
    SUMMARIZE (
        FILTER ( moves_fct, moves_fct[move_number] = 2 ),
        moves_fct[moves],
        dim_game[game_id]
    )
VAR _blackcountfirstmove =
    GROUPBY (
        _blackwintable,
        moves_fct[moves],
        "@count", SUMX ( CURRENTGROUP (), 1 )
    )
VAR _blackmaxwin =
    MAXX ( _blackcountfirstmove, [@count] )
RETURN
    SWITCH (
        SELECTEDVALUE ( dim_game[winner] ),
        "White", _whitemaxwin,
        "Black", _blackmaxwin
    )
```

<br />

(3) The third inquiry focuses on identifying the player with the highest number of wins and computing their winning percentage when competing against opponents with superior ratings. To present these findings effectively, I have chosen to employ a stacked bar chart. To provide valuable insights, I have designed the chart to showcase the top 10 winning players, along with their respective win counts against lower-rated opponents. I've also created an additional measure to display this supplementary information.

Regarding the data labels, while the chart effectively represents the win count against higher-rated opponents, I've opted not to directly display the win count against lower-rated opponents. Instead, I've chosen to depict the ratio of the win count against higher-rated opponents. This approach allows for the presentation of all pertinent and critical information, including the win count against higher-rated opponents, the ratio, the total win count, and, of course, the name of the player with the most wins, alongside the names of the other top 10 winning players.

![top10 winning players](/5-Power%20BI/assets/top10%20winning%20players.jpg)

The additinoal DAX measures utilized on this page is composed as follows.

```dax
Win count when oponent is lower rated = 
    [Winning count by player] - [Win count when oponent is higher rated]
```

<br />

(4) The fourth inquiry centers around calculating the percentage of wins achieved by higher-rated players. In this instance, I have chosen to present this data using a bar chart, similar to the approach I employed when addressing the first question. Additionally, I have integrated a card visualization that I previously crafted.

To generate this visual representation, I have slightly adjusted the formulation of the DAX measure. Notably, it is designed to solely display the win count when the victor holds a higher rating. You may observe that the total number of games (20,058) does not align precisely with the sum of each row. This discrepancy arises because the DAX measure employs a condition of "greater than" or "less than," and does not encompass the "equal to" condition. However, it is imperative to note that the decision to exclude winning counts against equally rated opponents was made deliberately, as it aligns with the objective of calculating the percentage of wins by higher-rated players. This decision should always be communicated and made in collaboration with the business owner or relevant stakeholders.

Regarding the display of data labels, I have chosen to maintain the same approach (Custom label) as I employed when addressing the first question. This consistency ensures clarity and coherence in the visualization.


![higher rate win count](/5-Power%20BI/assets/higher%20rated%20win%20count.jpg)

The additinoal DAX measures utilized on this page is composed as follows.

```dax
Higher rated win count =
SWITCH (
    SELECTEDVALUE ( dim_game[winner] ),
    "White",
        COUNTROWS (
            FILTER ( dim_game, dim_game[white_rating] > dim_game[black_rating] )
        ),
    "Black",
        COUNTROWS (
            FILTER ( dim_game, dim_game[white_rating] < dim_game[black_rating] )
        ),
    COUNTROWS ( dim_game )
)
```

```dax
Higher rated win count ratio =
VAR _allgames =
    CALCULATE (
        COUNTROWS ( dim_game ),
        REMOVEFILTERS ( dim_game[winner], dim_game[winner sort order] )
    )
VAR _higherratedwincount = [Higher rated win count]
RETURN
    DIVIDE ( _higherratedwincount, _allgames )
```

```dax
Higher rated win label =
FORMAT ( [Higher rated win count], "#,#0" ) & " | "
    & FORMAT ( [Higher rated win count ratio], "#0.00%" )
```

<br />

(5) The final inquiry pertains to identifying the initial move for Black that boasts the highest probability of securing victory following White's first move of D4. While crafting the Proof of Concept (POC) version, I ascertained that when White initiates with D4, the most advantageous response for Black is D5. In pursuit of providing even more valuable insights to end users stakeholders, I took a step further to determine Black's most winning move following any of White's opening moves.

To accomplish this, I opted to construct a table visualization, showcasing only the first move in each game, and subsequently, to analyze and discern the optimal subsequent move for Black. This analysis encompasses the frequency of the black's first move occurrence and its corresponding win ratio. Let there be no confusion; it's essential to remember that the move designated as number 1 represents White's initial play in the context of a chess game, whereas move number 2 signifies Black's opening move.

![black best first move](/5-Power%20BI/assets/black%20best%20first%20move.jpg)

The additinoal DAX measures utilized on this page is composed as follows.

```dax
Black most winning move after white first move = 
VAR _blackwinafterwhitefirstmove =
    // Retrieve the game IDs for games where black emerges as the winner.
    SUMMARIZE (
        FILTER (
            SUMMARIZE ( moves_fct, dim_game[game_id], dim_game[winner] ),
            dim_game[winner] = "Black"
        ),
        dim_game[game_id]
    )
VAR _blackfirstmoveofthegame =
    FILTER (
        ALL ( moves_fct ),
        moves_fct[game_id]
            IN _blackwinafterwhitefirstmove
                && moves_fct[move_number] = 2
    )
VAR _groupbyblackfirstmovecount =
    GROUPBY (
        _blackfirstmoveofthegame,
        moves_fct[moves],
        "@count", SUMX ( CURRENTGROUP (), 1 )
    )
VAR _maxcount =
    MAXX ( _groupbyblackfirstmovecount, [@count] )
RETURN
    MAXX (
        FILTER ( _groupbyblackfirstmovecount, [@count] = _maxcount ),
        moves_fct[moves]
    )
```
* Link to learn ALL DAX function: [Link](https://learn.microsoft.com/en-us/dax/all-function-dax?wt.mc_id=DP-MVP-5004989)

```dax
Black winning count after white first move = 
VAR _blackwinafterwhitefirstmove =
    // Retrieve the game IDs for games where black emerges as the winner.
    SUMMARIZE (
        FILTER (
            SUMMARIZE ( moves_fct, dim_game[game_id], dim_game[winner] ),
            dim_game[winner] = "Black"
        ),
        dim_game[game_id]
    )
VAR _blackfirstmoveofthegame =
    FILTER (
        ALL ( moves_fct ),
        moves_fct[game_id]
            IN _blackwinafterwhitefirstmove
                && moves_fct[move_number] = 2
    )
VAR _groupbyblackfirstmovecount =
    GROUPBY (
        _blackfirstmoveofthegame,
        moves_fct[moves],
        "@count", SUMX ( CURRENTGROUP (), 1 )
    )
VAR _maxcount =
    MAXX ( _groupbyblackfirstmovecount, [@count] )
RETURN
    _maxcount
```

<br />

```dax
Black winning ratio after white first move = 
VAR _blackwinafterwhitefirstmove =
    //Retrieve the game IDs for games where black emerges as the winner.
    SUMMARIZE (
        FILTER (
            SUMMARIZE ( moves_fct, dim_game[game_id], dim_game[winner] ),
            dim_game[winner] = "Black"
        ),
        dim_game[game_id]
    )
VAR _gamescount =
    COUNTROWS ( SUMMARIZE ( moves_fct, dim_game[game_id] ) )
VAR _blackfirstmoveofthegame =
    FILTER (
        ALL ( moves_fct ),
        moves_fct[game_id]
            IN _blackwinafterwhitefirstmove
                && moves_fct[move_number] = 2
    )
VAR _groupbyblackfirstmovecount =
    GROUPBY (
        _blackfirstmoveofthegame,
        moves_fct[moves],
        "@count", SUMX ( CURRENTGROUP (), 1 )
    )
VAR _maxcount =
    MAXX ( _groupbyblackfirstmovecount, [@count] )
RETURN
    DIVIDE ( _maxcount, _gamescount )
```

<br />

While constructing a table visualization to pinpoint the initial move by Black that exemplifies the most successful winning strategy, I also delved further to determine the subsequent White move that maximizes the chances of victory. The results of this table visualization are presented below.

![white move number 3 most winning move](/5-Power%20BI/assets/white%20most%20winning%20move%20(move%203).jpg)

The additinoal DAX measures utilized on this page is composed as follows.

```dax
White most winning move after black first move = 
VAR _blackfirstmove = [Black most winning move after white first move]
VAR _moveonegameid =
    VALUES ( moves_fct[game_id] )
VAR _movetwogameid =  //Identify the game IDs in which the second move was made by black (as per the previous result), and white won.
    SUMMARIZE (
        FILTER (
            SUMMARIZE (
                FILTER (
                    ALL ( moves_fct ),
                    moves_fct[game_id]
                        IN _moveonegameid
                            && moves_fct[move_number] = 2
                            && moves_fct[moves] = _blackfirstmove
                ),
                dim_game[game_id],
                dim_game[winner]
            ),
            dim_game[winner] = "White"
        ),
        dim_game[game_id]
    )
VAR _whitesecondtmoveofthegame =
    // The second move for white players occurs on move number 3.
    FILTER (
        ALL ( moves_fct ),
        moves_fct[game_id]
            IN _movetwogameid
                && moves_fct[move_number] = 3
    )
VAR _groupbywhitesecondmovecount =
    GROUPBY (
        _whitesecondtmoveofthegame,
        moves_fct[moves],
        "@count", SUMX ( CURRENTGROUP (), 1 )
    )
VAR _maxcount =
    MAXX ( _groupbywhitesecondmovecount, [@count] )
RETURN
    MAXX (
        FILTER ( _groupbywhitesecondmovecount, [@count] = _maxcount ),
        moves_fct[moves]
    )
```
* Link to learn VALUES DAX function: [Link](https://learn.microsoft.com/en-us/dax/values-function-dax?wt.mc_id=DP-MVP-5004989)

<br />

```dax
White winning count after black first move = 
VAR _blackfirstmove = [Black most winning move after white first move]
VAR _moveonegameid =
    VALUES ( moves_fct[game_id] )
VAR _movetwogameid =  //Determine the game IDs where, in the previous result, move number 2 represents black's first move and the game results in a white player's victory.
    SUMMARIZE (
        FILTER (
            SUMMARIZE (
                FILTER (
                    ALL ( moves_fct ),
                    moves_fct[game_id]
                        IN _moveonegameid
                            && moves_fct[move_number] = 2
                            && moves_fct[moves] = _blackfirstmove
                ),
                dim_game[game_id],
                dim_game[winner]
            ),
            dim_game[winner] = "White"
        ),
        dim_game[game_id]
    )
VAR _whitesecondtmoveofthegame =
    //The second move for white players occurs on move number 3.
    FILTER (
        ALL ( moves_fct ),
        moves_fct[game_id]
            IN _movetwogameid
                && moves_fct[move_number] = 3
    )
VAR _groupbywhitesecondmovecount =
    GROUPBY (
        _whitesecondtmoveofthegame,
        moves_fct[moves],
        "@count", SUMX ( CURRENTGROUP (), 1 )
    )
VAR _maxcount =
    MAXX ( _groupbywhitesecondmovecount, [@count] )
RETURN
    _maxcount
```

<br />

```dax
White winning ratio after black first move = 
VAR _blackfirstmove = [Black most winning move after white first move]
VAR _moveonegameid =
    VALUES ( moves_fct[game_id] )
VAR _movetwogameidall =
    SUMMARIZE (
        FILTER (
            ALL ( moves_fct ),
            moves_fct[game_id]
                IN _moveonegameid
                    && moves_fct[move_number] = 2
                    && moves_fct[moves] = _blackfirstmove
        ),
        dim_game[game_id],
        dim_game[winner]
    )
VAR _movetwogamecount =
    COUNTROWS ( _movetwogameidall )
VAR _movetwogameid =
    //Identify game IDs where move number 2 corresponds to black's first move (from the previous result), and the outcome of the game is a white player's victory.
    SUMMARIZE (
        FILTER ( _movetwogameidall, dim_game[winner] = "White" ),
        dim_game[game_id]
    )
VAR _whitesecondtmoveofthegame =
    //The second move for white players occurs on move number 3.
    FILTER (
        ALL ( moves_fct ),
        moves_fct[game_id]
            IN _movetwogameid
                && moves_fct[move_number] = 3
    )
VAR _groupbywhitesecondmovecount =
    GROUPBY (
        _whitesecondtmoveofthegame,
        moves_fct[moves],
        "@count", SUMX ( CURRENTGROUP (), 1 )
    )
VAR _maxcount =
    MAXX ( _groupbywhitesecondmovecount, [@count] )
RETURN
    DIVIDE ( _maxcount, _movetwogamecount )
```

<br />

(6) To facilitate the productionization of the Power BI report, I opted to conceal all the pages I had previously crafted for data and data model validation. Instead, I created a single page that systematically incorporates all visualizations, thereby presenting stories and insights. Additionally, it is feasible to retain this Power BI file as a proof of concept (POC) version and initiate the development of a new one intended for production use. It's worth noting that designing of the report page falls outside the purview of this course, but ample resources are available for reference and those are easily found on web.

![power bi report product](5-Power%20BI/assets/pbi%20report%20production.jpg)

<span style="color:green">*Note: The DAX measures I've crafted above may not necessarily represent the most optimal performance and some of them might appear rather intricate to navigate and understand. However, it's essential to delve into each line of the formula to comprehend the specific outcome I intend to achieve. The primary goal is to ensure that the results meet the requirements of the report viewers. Subsequently, I can explore ways to improve the DAX measures for better performance, if necessary.*</span>

<br />
<br />

## <a name="chapter7"></a>7. Publishing and Sharing Power BI report 

### Create a workspace within the Power BI Service (<https://app.powerbi.com>) and distribute the Power BI report

Upon completion of the Power BI report authoring, it's time to embark on the process of publication and dissemination to relevant stakeholders. For details regarding the requisite Power BI licensing for both Power BI developer and the audience to facilitate seamless sharing and report access, please refer to the provided link below.

* Link to learn Licensing the Power BI service: [Link](https://learn.microsoft.com/en-us/power-bi/enterprise/service-admin-licensing-organization?wt.mc_id=DP-MVP-5004989)

Here's a concise outline of the steps to publish and share Power BI report. These steps will help streamline the process of publishing and sharing the Power BI report effectively.

(1) Navigate to <https://app.powerbi.com> and initiate the creation of a workspace.

![create workspace](/5-Power%20BI/assets/create%20workspace.jpg)

* Link to learn Power BI service per user and capacity based licenses: [Link](https://learn.microsoft.com/en-us/power-bi/fundamentals/service-features-license-type?wt.mc_id=DP-MVP-5004989)

<br />

(2) Save the Power BI desktop file and proceed to publish it directly into the designated workspace.

<br />

(3) Access the respective workspace housing your report.

![publish to workspace](/5-Power%20BI/assets/publish%20to%20workspace.jpg)

<br />

(4) Verify that the report has been published accurately, ensuring it is accessible as intended.

![pbi report in workspace](/5-Power%20BI/assets/pbi%20report%20in%20worksapce.jpg)

<br />

(5) If necessary, configure the dataset refresh settings to suit your specific requirements.

![configure refresh dataset](/5-Power%20BI/assets/configure%20refresh%20dataset.jpg)

<br />

(6) After deciding who should have access to this Power BI report, I can grant them access to the workspace. As the creator and administrator of the workspace, I have the authority to assign people to all different roles. Typically, I assign individuals as viewers, and this choice ensures that, for instance, the Row-Level Security (RLS) configuration functions correctly.

![manage access to workspace](/5-Power%20BI/assets/manage%20access%20to%20workspace.jpg)

* Link to learn Roles in workspace in Power BI: [Link](https://learn.microsoft.com/en-us/power-bi/collaborate-share/service-roles-new-workspaces?wt.mc_id=DP-MVP-5004989)


<br />
<br />

## <a name="chapter8"></a>8. Closing 

In the pursuit of mastering Power BI, I embarked on an engaging journey of discovery, choosing the intriguing domain of Chess Game data as the canvas to analyze and visualize invaluable insights. 

Throughout this course, we've delved into the following key aspects:

1. **Sample Data:** Setting the stage with the foundation of our analysis.
2. **Unlocking the Power of Power BI:** Unraveling the capabilities and potential of this robust tool.
3. **Data Modeling:** Crafting a structured and efficient data model.
4. **Opening Power BI Desktop:** Initiating our journey in the Power BI ecosystem.
5. **DAX Measures and Visualizations (Proof of Concept):** Experimenting with the power of Data Analysis Expressions and visualizations to lay the groundwork.
6. **DAX Measures and Visualizations (Production):** Elevating our analysis to production-ready status.
7. **Publishing and Sharing the Power BI Report:** The final step, where we disseminate our insights to stakeholders, ensuring that our data-driven narratives are shared and utilized for informed decision-making.

As I conclude this learning experience, it is important to remember that the knowledge and skills acquired in this course are not merely a conclusion but a beginning. Power BI is a dynamic tool that continues to evolve, and our ability to harness its capabilities will grow with it. Embrace the ever-expanding world of data visualization, and use your newfound expertise to bring meaningful insights to life, driving transformative decisions and innovation. The journey of data exploration is an ongoing one, and I encourage you to keep exploring, learning, and creating with Power BI. 

Thank you for joining me on this adventure, and best of luck in your data-driven endeavors.

<br />
<br />

<span style="color:green">Author: Jihwan Kim | Microsoft MVP | Link to profile: [Link](https://mvp.microsoft.com/en-US/mvp/profile/385eb34e-c755-ed11-9561-000d3a197333)</span>