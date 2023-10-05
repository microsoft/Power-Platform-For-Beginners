# Power BI

   - Understanding data visualization principles and best practices.
   - Connecting to various data sources and transforming data.
   - Creating interactive reports and dashboards.
   - Implementing data modeling and calculations.
   - Sharing and collaborating on Power BI content.


# Power BI for Beginner – Chess Game Analysis 

   - Written by Jihwan Kim / Microsoft MVP 

 

# Timeline / Plans 

- 2023/09/17 

   Decide what type of data to use, and what analysis may help end users to have valuable insights. 

   Share about what Power BI is briefly. 

   Share plans. 

- 2023/9/24 

   Describe how to draw Datamodel (fact tables, dimension tables), and explain how to import data into the Power BI Power Query Editor. 

- 2023/10/01 

   Load it to Lakehouse, import it into Power BI Desktop, transform data in the Power Query Editor, and create a datamodel (Import mode). 

- 2023/10/08 

   Create DAX measures and visualizations 

- 2023/10/15 

   Fix and check the report. 

- 2023/10/22 

   Personal trip. 

- 2023/10/29 

   Fix and check the documentation. 

 
# 2023/09/17 

## Sample data: Online Chess Games 

It is an open source that I get from Mavenanalytics.io 

Link to the website: https://mavenanalytics.io/data-playground?page=5&pageSize=5 

Link to the file: https://1drv.ms/x/s!AvmCO4Wm--vEvDmDfSBEYGGHEMFI?e=gWy1Ig 


## Purpose of the course 

This course is designed to provide guidance systematically through the fundamentals of Power BI. Several key concepts, but only the basics, will be illustrated using the sample dataset, and by the end of the course, we will have constructed a Power BI report. You can actively participate in the tutorial by downloading the dataset from the link above. The datamodel and the process to create the analysis report that are described in this course is not an absolute and the only solution, but there might be several different ways to have the same result. The purpose of this course is to make Power BI starters have more fun in learning Power BI. If readers want to skip storing the source file or the source data in Fabric Lakehouse, the CSV file can be used from the your local computer and can be easily imported into Power BI Desktop.   
  

## What Is Power BI? 

Power BI is a tool that enables you to establish connections with various data sources, visualize data through reports and dashboards, and subsequently distribute them to the individuals of your choice. 
 
Power BI consists of three primary components:  

1. Power BI Desktop: This is a no-cost desktop application for creating and designing reports.  

2. Power BI Service: It's an online publishing service for viewing and sharing reports and dashboards.  

3. Power BI mobile apps: These apps facilitate the access and viewing of reports and dashboards while you're on the move. 

In this course, I will focus on configuring and connecting to the source (Lakehouse), creating and designing a report in the Power BI Desktop, and very briefly about how to share it via Power BI Service. 

You need to register and have Power BI Service ID/PW (https://app.powerbi.com) in order to move the CSV file from the local machine to Lakehouse as a source.  
  

## What Is the Purpose of Power BI? 

Power BI belongs to the realm of Business Intelligence (BI) tools. The overarching goal of BI is to monitor Key Performance Indicators (KPIs) and unveil valuable insights within business data, enhancing decision-making processes throughout the entire organization.  

The utilization of Power BI varies according to individual roles, encompassing developers, analysts, managers, directors, and all other personnel within an organization. 
 

## Suggested Analyses by using the sample data:  

What to show in the analysis report is communicated frequently and shared with end users as a poc (proof of concept) version before we start to create the Power BI report. 

We, as a Power BI Report developer, have to share with end users about, 

- What users want to see in the report 

- What users need to see in the report 

- What values and insights users can get from the report 

By using the sample data, I pretend and assume that I had conversations with users a few times about what we agreed to describe on the report, and those are, 

1. What is the next best move to win the game, and what is the winning percentage of the move based on the historical data that we have (the data has 20,051 games information)? 

2. What proportion of games were secured by the white player, and how many concluded as draws?  

3. Which initial chess move was employed most frequently in games where black emerged victorious? Conversely, what was the prevalent opening move in games where white emerged as the winner?  

4. What percentage of games were won by the participant with the superior rating? Is there any variance in this statistic based on the color of pieces?  

5. Who is the user with the highest number of game wins? What percentage of these victories did the user achieve as the higher-rated player?



# 2023/09/24 

## Draw a datamodel  

After having conversation with stakeholders, the main insights that need be shown by the analysis are, 

- Win or lose by players 

- Which next moves makes the game Win or lose

The dimension tables contain information about the Players and Games. And the fact table contains information about Moves. 

The drawing of the datamodel looks like below figure. The below datamodel can be changed or amended based on what data is in the source, or based on how we proceed to create a proper analysis report. 

![Datamodel planning](/5-Power%20BI/assets/Datamodel%20plan.jpg) 

 

## Store the source in Lakehouse  

The source is given as a CSV file. I decide to store this source data in Fabric Lakehouse, and I plan to use Dataflow Gen2 to transform the source table and load it back to Lakehouse. 

1. Create a workspace in app.powerbi.com 
2. Name the new workspace “PBI_For_Beginner”.

![Create Fabric workspace](/5-Power%20BI/assets/Create%20Fabric%20workspace.jpg)

3. Create Lakehouse, and name it as “pbiforbeginner”. 

![Create Lakehouse](/5-Power%20BI/assets/Create%20Lakehouse.jpg)

4. Upload the CSV file.

![Upload CSV to Lakehouse](/5-Power%20BI/assets/Upload%20CSV%20to%20Lakehouse.jpg)

5. Now, the file is in the Lakehouse.  

6. Load it to the table.

![Make CSV to Table in Lakehouse](/5-Power%20BI/assets/Make%20CSV%20to%20Table%20in%20Lakehouse.jpg)

7. Once it is loaded, the source in the Lakehouse looks like below.  

![View a table in Lakehouse](/5-Power%20BI/assets/View%20a%20table%20in%20Lakehouse.jpg)

8. From the next step, the table in Lakehouse is used in Dataflow Gen2 to be transformed to have proper dimension table and fact table. This is a more practical way in some cases, but in this course, I will briefly show how to create Dataflow Gen2 and load it back to Lakehouse in order to let you slightly feel about what Dataflow Gen2 is. In this course, the majority of transformation will be done in Power BI Desktop Power Query Editor.  

9. Create Dataflow Gen2.

![Create Dataflow Gen2](/5-Power%20BI/assets/Create%20Dataflow%20Gen2.jpg)

10. Connect to Lakehouse (pbiforbeginner).

![Connect to Lakehouse](/5-Power%20BI/assets/Dataflow%20Gen2%20connect%20to%20Lakehouse%20step%201.jpg)

![Connect to Lakehouse](/5-Power%20BI/assets/Dataflow%20Gen2%20connect%20to%20Lakehouse%20step%202.jpg)

11. Rename Dataflow Gen2 as “Chess_Games” and publish it later to save it up to this step.

![Dataflow Gen2 save](/5-Power%20BI/assets/Dataflow%20Gen2%20save.jpg)


# 2023/10/01 

## From this step, it is to load data back to Lakehouse, import it into Power BI Desktop, transform data in the Power Query Editor, load it to Power BI and create a datamodel in Power BI. 


12. Select Data destination as Lakehouse. 

![Dataflow Gen2 destination](/5-Power%20BI/assets/Dataflow%20Gen2%20destination.jpg)

![Dataflow Gen2 destination lakehouse](/5-Power%20BI/assets/Dataflow%20Gen2%20dest%20lakehouse.jpg)

![Dataflow Gen2 dest tablename](/5-Power%20BI/assets/Dataflow%20Gen2%20dest%20tablename.jpg)

![Dataflow Gen2 dest replace](/5-Power%20BI/assets/Dataflow%20Gen2%20dest%20replace.jpg)

![Dataflow Gen2 publish](/5-Power%20BI/assets/Dataflow%20Gen2%20publish.jpg)

13. Once the loading of “Chess_Games” Dataflow Gen2 is done, go to “pbiforbeginner” Lakehouse to check whether the “chess_games_source” is added.

![Lakehouse contains new table from Dataflow Gen2](/5-Power%20BI/assets/Lakehouse%20contains%20new%20table%20from%20dataflow%20gen2.jpg)

14. This table is the same as “chess_games” table that is located above in the same folder. The steps that are operated in Dataflow Gen2 are not necessary in this case, however, if you do more table transforms steps in Dataflow Gen2, the result will be different. In this course, I decided to do more table transforms steps later in Power BI Desktop Power Query Editor. 

15. Open Power BI Desktop and connect to pbiforbeginner Lakehouse.

![pbi desktop connect to lakehouse](/5-Power%20BI/assets/pbi%20desktop%20connect%20to%20lakehouse.jpg)


![lakehouse select](/5-Power%20BI/assets/lakehouse%20select.jpg)

![lakehouse table import](/5-Power%20BI/assets/lakehouse%20table%20import.jpg)

16. “chess_games_source” table is imported into Power Query Editor. Because this is the source for dimension tables and a fact table, which are loaded later into the Power BI report to create a datamodel, [Enable load] is unchecked (the same meaning as disable load) and reference this source table to create dimension tables and a fact table. 

![pq editor disable load](/5-Power%20BI/assets/pq%20editor%20disable%20load.jpg)

17. Create dim_player table. 

![pq editor dim table](/5-Power%20BI/assets/pq%20editor%20dim%20table.jpg)

18. Follow the transformation steps in the query. M codes are described in “Advanced Editor” in detail. The brief explanation of this transformation is,  

- Get black id column and white id column.
- Append two columns, make it one column, and name it as player_id column.
- Add index column to have id number

![pq editor dim table final](/5-Power%20BI/assets/pq%20editor%20dim%20table%20final.jpg)


![dim table advanced editor](/5-Power%20BI/assets/pq%20editor%20dim%20table%20advanced%20editor.jpg)


```
let 
    Source = chess_games_source,
    #"white id" = Table.SelectColumns(Source,{"white_id"}),
    #"rename it to player id (white)" = Table.RenameColumns(#"white id",{{"white_id", "player_id"}}),
    #"black id" = Table.SelectColumns(Source,{"black_id"}),
    #"rename it to palyer id (black)" = Table.RenameColumns(#"black id",{{"black_id", "player_id"}}),
    #"Appended Query" = Table.Combine({#"rename it to player id (white)", #"rename it to palyer id (black)"}),
    #"Removed Duplicates" = Table.Distinct(#"Appended Query"),
    #"Sorted Rows" = Table.Sort(#"Removed Duplicates",{{"player_id", Order.Ascending}}),
    #"Added Index" = Table.AddIndexColumn(#"Sorted Rows", "player_id_index", 1, 1, Int64.Type) 

in 
    #"Added Index" 
```

19. Reference the source table and create dim_game table.

![pq editor dim table](/5-Power%20BI/assets/pq%20editor%20dim%20table%20table.jpg)

20. Follow the transformation steps. M codes are described in “Advanced Editor” in detail. The description of this transformation is,
- Remove unnecessary columns. For instance, the moves column is for the fact table, not for the dimension table.
- Instead of showing white_id and black_id columns in this table, try to show white_player_id_index and black_player_id_index instead.

![advanced editor](/5-Power%20BI/assets/pq%20editor%20dim%20tabletable%20advaned%20editor.jpg)

 
```
let 
    Source = chess_games_source,
    #"Removed Other Columns" = Table.SelectColumns(Source,{"game_id", "rated", "turns", "victory_status", "winner", "time_increment", "white_id", "white_rating", "black_id", "black_rating", "opening_fullname", "opening_shortname"}),
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
 

21. Reference the source table and create moves_fct table. 

22. Follow the transformation steps. M codes are described in “Advanced Editor” in detail. The purpose of this transformation is to have,
- Select a column that contains all moves per game, and split into one move per row in the same game_id.
- Each move in each game_id has sequence number.

![pq editor fct table](/5-Power%20BI/assets/pq%20editor%20fct%20table.jpg)
 
```
let 
    Source = chess_games_source,
    #"Removed Other Columns" = Table.SelectColumns(Source,{"game_id", "moves"}),
    #"Split Column by Delimiter" = Table.ExpandListColumn(Table.TransformColumns(#"Removed Other Columns", {{"moves", Splitter.SplitTextByDelimiter(" ", QuoteStyle.Csv), let itemType = (type nullable text) meta [Serialized.Text = true] in type {itemType}}}), "moves"),
    #"Grouped Rows" = Table.Group(#"Split Column by Delimiter", {"game_id"}, {{"moves", each Table.AddIndexColumn( _, "move_number", 1, 1, Int64.Type)}}),
    #"Expanded moves" = Table.ExpandTableColumn(#"Grouped Rows", "moves", {"moves", "move_number"}, {"moves", "move_number"}),
    #"Changed Type" = Table.TransformColumnTypes(#"Expanded moves",{{"moves", type text}, {"move_number", Int64.Type}}) 

in 
    #"Changed Type" 
```

23. Close and apply to Power BI Desktop 

![load from pq to pbi](/5-Power%20BI/assets/load%20tables%20from%20pq%20to%20pbi.jpg)

 
24. Create relationships between tables. This is following the figure of the datamodel that is shown in the beginning of the course (figure01).  

25. Go to the model view, and drag one column from one table and connect it to the other column from another table. 

- dim_player[player_id_index] to dim_game[white_player_id_index]
- dim_player[player_id_index] to dim_game[black_player_id_index]
- dim_game[game_id] to moves_fct[game_id]
- Inactive relationship is described as dotted line, and the inactive relationship can be activated by writing a proper DAX function later. By clicking “Manage relationships”, the detailed information of each relationship is shown.

![datamodel view](/5-Power%20BI/assets/datamodel%20view.jpg)

![relationship manage view in pbi](/5-Power%20BI/assets/relationship%20manage%20view.jpg)
