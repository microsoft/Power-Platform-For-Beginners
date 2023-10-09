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

   Create DAX measures and visualizations to provide insights

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


## Purpose of this writing 

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

1. What is Black's optimal opening move that yields the highest probability of success following White's initial move of D4 (the data has 20,051 games information)? 

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

![Datamodel planning fix](/5-Power%20BI/assets/Datamodel%20plan%20fix.jpg) 

 

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

15. Open Power BI Desktop and connect to pbiforbeginner Lakehouse. When opening Power BI Desktop, login ID has to be the same as what I used when creating Lakehouse.

![pbi desktop connect to lakehouse](/5-Power%20BI/assets/pbi%20desktop%20connect%20to%20lakehouse.jpg)


![lakehouse select](/5-Power%20BI/assets/lakehouse%20select.jpg)

![lakehouse table import](/5-Power%20BI/assets/lakehouse%20table%20import.jpg)

Note: If you do not want to connect to Lakehouse, but if you want to import the CSV file directly from your local computer, please follow the steps below. One thing to keep in mind is that local files sometimes does not assign column title automatically. In this case, you can assign column title in Power Query Editor.
![import csv file](/5-Power%20BI/assets/PBI%20Desktop%20connect%20to%20CSV%20file.jpg)
![use first row as headers](/5-Power%20BI/assets/PQEditor%20use%20first%20row%20as%20headers.jpg)


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

-- Note: The below M code is with comments after "//" that describes what does each step mean. The whole M code can be copy-pasted into Advanced Editor in Power Query Editor.

```
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

19. Reference the source table and create dim_game table.

![pq editor dim table](/5-Power%20BI/assets/pq%20editor%20dim%20table%20table.jpg)

20. Follow the transformation steps. M codes are described in “Advanced Editor” in detail. The description of this transformation is,
- Remove unnecessary columns. For instance, the moves column is for the fact table, not for the dimension table.
- Instead of showing white_id and black_id columns in this table, try to show white_player_id_index and black_player_id_index instead.

![advanced editor](/5-Power%20BI/assets/pq%20editor%20dim%20tabletable%20advaned%20editor.jpg)

 
```
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
 

21. Reference the source table and create moves_fct table. 

22. Follow the transformation steps. M codes are described in “Advanced Editor” in detail. The purpose of this transformation is to have,
- Select a column that contains all moves per game, and split into one move per row in the same game_id.
- Each move in each game_id has sequence number.

![pq editor fct table](/5-Power%20BI/assets/pq%20editor%20fct%20table.jpg)
 
```
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

23. Close and apply to Power BI Desktop 

![load from pq to pbi](/5-Power%20BI/assets/load%20tables%20from%20pq%20to%20pbi.jpg)

 
24. Create relationships between tables. This is following the figure of the datamodel that is shown in the beginning of the course (figure01).  

25. Go to the model view, and drag one column from one table and connect it to the other column from another table. 

- dim_player[player_id_index] to dim_game[white_player_id_index]
- dim_player[player_id_index] to dim_game[black_player_id_index]
- dim_game[game_id] to moves_fct[game_id]
- Inactive relationship is described as dotted line, and the inactive relationship can be activated by writing a proper DAX function (for instance, "USERELATIONSHIP" DAX function) when it is needed. By clicking “Manage relationships”, the detailed information of each relationship is shown.

![datamodel view](/5-Power%20BI/assets/datamodel%20view.jpg)

![relationship manage view in pbi](/5-Power%20BI/assets/relationship%20manage%20view.jpg)


# 2023/10/08 

## Create DAX measures and visualizations to provide insights. 

There are two links from Microsoft useful to see and understand before starting this session. 

Learn concept of DAX by video Link: https://learn.microsoft.com/en-us/dax/dax-learn-videos?wt.mc_id=DP-MVP-5004989 

DAX Glossaries Link: https://learn.microsoft.com/en-us/dax/dax-glossary?wt.mc_id=DP-MVP-5004989 
 

1. Before creating visualizations and DAX measures, try to understand the concept of DAX (Data Analysis Expressions), and the above two links created by Microsoft are very useful to start with understanding the concept of DAX. 

2. At the beginning of this writing, I talked about what conversation I had with stakeholders who will see this report. In the conversation, we talked about 5 topics, and I would like to rewrite those like below ordering by how easy and smooth it is to provide insights. 
 

- What proportion of games were secured by the white player, and how many concluded as draws? 
- Which initial chess move was employed most frequently in games where black emerged victorious? Conversely, what was the prevalent opening move in games where white emerged as the winner?
- Who is the user with the highest number of game wins? What percentage of these victories did the user achieve as the higher-rated player?
- What percentage of games were won by the participant with the superior rating? Is there any variance in this statistic based on the color of pieces?
- What is the initial move for Black that demonstrates the highest likelihood of winning after White's first move of D4?
 

3. Let’s create visualizations and DAX measures based on the above request. The first request is, to simplify it further, we want to know how many games were won, lost, or drawn by white and black players.

4. In order to consolidate DAX measures in an organized way, I create a blank table, and name it as “Key_Measures”. This table will contain only DAX measures. 
![create measure table](/5-Power%20BI/assets/create%20measure%20table.jpg)
 

5. On the blank canvas, insert a table visualization and drag the [winner] column from dim_game table. The final visualization may not be a table visualization. However, this helps to see and understand what information needs to be shown and created in the visualization. 

6. Create a DAX measure that counts wins by black, white, or draws. Currently, the order in the table visualization is alphabetical, displaying Black, Draw, and then White. To correct the order and have it appeared as White, Black, and Draw, we need to create a new column in the same table in Power Query Editor that describes White = 1, Black = 2, and Draw = 3. And then, we can order [winner] column by the new column that we just created. In Power Query Editor, a new column can be created by just adding a step by clicking fx button in the formular bar or add M code after opening Advanced Editor. 
![analysis01](/5-Power%20BI/assets/analysis01.jpg)
![analysis01pwerqueryeditor](/5-Power%20BI/assets/analysis01PQeditor.jpg) 
![analysis01powerqueryadvancededitor](/5-Power%20BI/assets/analysis01pqadvancededitor.jpg)

```
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

7. Close and apply Power Query Editor and configure sort order.

![sort column](/5-Power%20BI/assets/sort%20column.jpg) 

8. Create DAX measure. As described in the below, the answer to the first request is,  

- Total 20,058 games 
- White wins 10,001 games 
- Black wins 9,107 games 
- Draw happens in 950 games 

![analysis 01 result](/5-Power%20BI/assets/analysis01result.jpg)

```
Win count = 
    DISTINCTCOUNT(dim_game[game_id])
```
* Link to learn DISTINCTCOUNT DAX function: https://learn.microsoft.com/en-us/dax/distinctcount-function-dax?wt.mc_id=DP-MVP-5004989

9. The second request is, if I rephrase it, what is the most first move played in the black winning game and in the white winning game? In order to answer this, the following DAX measures are written and those are used in New Card visualization. [The most winning first move by white] DAX measure is written with comments inside the formula, and it explains what the meaning of each variable is. All other measures that are used in this page are written in a very similar way with [The most winning first move by white] DAX measure. Do not be confused that the black players’ first move is always move_number = 2. The answer to the second request is, 

- The move e4 is the most played winning first move of white players 
- The move e5 is the most played winning first move of black players 
- White players win 6371 games when the first move is e4 
- Black players win 3101 games when the first move is e5 

![analysis02](/5-Power%20BI/assets/analysis02.jpg)

```
The most winning first move by white = 

VAR _whitewintable =  //Create a virtual table that shows white players win with showing the first move of each game.
    FILTER (
        SUMMARIZE (
            FILTER ( moves_fct, moves_fct[move_number] = 1 ),
            moves_fct[moves],
            dim_game[game_id],
            dim_game[winner]
        ),
        dim_game[winner] = "White"
    )

VAR _countfirstmove =   // Group every first move in the above table with adding counting column. 
    GROUPBY (
        _whitewintable,
        moves_fct[moves],
        "@count", SUMX ( CURRENTGROUP (), 1 )
    )

VAR _maxwin =   // Maximum counting number means the most played first move.
    MAXX ( _countfirstmove, [@count] )

VAR _mostwinningfirstmove =
    FILTER ( _countfirstmove, [@count] = _maxwin )
    
RETURN
    CONCATENATEX ( _mostwinningfirstmove, moves_fct[moves], ", " )
```
* Link to learn FILTER DAX function: https://learn.microsoft.com/en-us/dax/filter-function-dax?wt.mc_id=DP-MVP-5004989
* Link to learn SUMMARIZE DAX function: https://learn.microsoft.com/en-us/dax/summarize-function-dax?wt.mc_id=DP-MVP-5004989
* Link to learn GROUPBY DAX function: https://learn.microsoft.com/en-us/dax/groupby-function-dax?wt.mc_id=DP-MVP-5004989
* Link to learn MAXX DAX function: https://learn.microsoft.com/en-us/dax/maxx-function-dax?wt.mc_id=DP-MVP-5004989
* Link to learn CONCATENATEX DAX function: https://learn.microsoft.com/en-us/dax/concatenatex-function-dax?wt.mc_id=DP-MVP-5004989


```
The most winning first move by black = 

VAR _blackwintable =    // black player's first move is always move number 2
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

```
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

```
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

10. The third request, rephrased for clarity, is to identify the player with the most wins and calculate their winning percentage against opponents with a higher rating. After creating a table visualization like below, when clicking the three dots located in the upper right side of the table visualization, you can sort by any DAX measure that is used in the visualization. Or you can simply click the measure name itself in the visualization. The answer to this question is, 

- Player id = taranga wins 72 games. 
- And out of the 72 games played, 36 were won against higher-rated opponents (50%). 

![analysis03](/5-Power%20BI/assets/analysis03.jpg)

```
Winning count by player = 

VAR _whiteplay =
    COUNTROWS ( FILTER ( dim_game, dim_game[winner] = "White" ) )

//activating inactive relationship in the datamodel by using USERELATIONSHIP DAX function    
VAR _blackplay =    
    CALCULATE (
        COUNTROWS ( FILTER ( dim_game, dim_game[winner] = "Black" ) ),
        USERELATIONSHIP ( dim_player[player_id_index], dim_game[black_player_id_index] )
    )
    
RETURN
    _whiteplay + _blackplay
```
* Link to learn COUNTROWS DAX function: https://learn.microsoft.com/en-us/dax/countrows-function-dax?wt.mc_id=DP-MVP-5004989
* Link to learn USERELATIONSHIP DAX function: https://learn.microsoft.com/en-us/dax/userelationship-function-dax?wt.mc_id=DP-MVP-5004989
* Link to learn CALCULATE DAX function: https://learn.microsoft.com/en-us/dax/calculate-function-dax?wt.mc_id=DP-MVP-5004989


```
Win count when oponent is higher rated = 

VAR _wincountbywhite =
    COUNTROWS (
        FILTER (
            dim_game,
            dim_game[winner] = "White"
                && dim_game[white_rating] < dim_game[black_rating]
        )
    )

//activating inactive relationship in the datamodel by using USERELATIONSHIP DAX function    
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

```
Winning higher rated player percentage = 
DIVIDE( [Win count when oponent is higher rated], [Winning count by player] )
``` 
* Link to learn DIVIDE DAX function: https://learn.microsoft.com/en-us/dax/divide-function-dax?wt.mc_id=DP-MVP-5004989



11. The fourth request is to calculate how much the percentage of wins is by higher rated players. And the answer to this is,
- 61.58%. 

    This can be described in a table visualization or in a card visualization like below. 

![analysis04 table visualization](/5-Power%20BI/assets/analysis04tablevisual.jpg)
![analysis04 card visualization](/5-Power%20BI/assets/analysis04cardvisual.jpg)

```
White higher rated win count = 

COUNTROWS (
    FILTER (
        dim_game,
        dim_game[white_rating] > dim_game[black_rating]
    )
)
```

```
Black higher rated win count = 

COUNTROWS (
    FILTER (
        dim_game,
        dim_game[white_rating] < dim_game[black_rating]
    )
)
```

```
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

12. The final question, expressed in a more straightforward manner, is, after White plays the first move D4, what is the most advantageous opening move for Black in terms of achieving the highest winning percentage?
    
    The thinking process is like below and this helps to create DAX measure in more intuitive way.
- Begin by filtering the moves_fct table to include only instances where the first move is D4.
- Utilize this criterion to identify games that were won by Black from the dim_game table.
- To the resulting table, introduce a new column that calculates the move number as 2.
- Group the table by move number = 2 and calculate the count.
- Determine the highest count number among these counts.
- Identify the move that corresponds to the highest count number, as it shares the same count value as the highest count number.

![analysis05](/5-Power%20BI/assets/analysis05.jpg)

```
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
* Link to learn ADDCOLUMNS DAX function: https://learn.microsoft.com/en-us/dax/addcolumns-function-dax?wt.mc_id=DP-MVP-5004989

