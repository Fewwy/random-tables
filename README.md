# random-tables
A tool to create and roll on random tables for Tabletop RPGs

In the future, the plan is to have a User Interface that will allow you to easily construct your own tables, but that functionality will take a while to build.  
Currently, if you wish to customize your tables, you may do so by editing the ***public/js/tableData.js*** file.

## To Run

Download the project and place the Public folder somewhere convenient.

In your web browser, open the **public/index.html** file.

It will automatically load in whatever data is in the ***pubic/js/tableData.js*** file.

Hit the "roll table" button to get a random result.  Click on the actual table entries to expand sub-tables.

## To Edit Tables

Table Data is contained in the ***public/js/tableData.js*** file.  

There is one master table (in the example, it is `encounterChances`, at line 91 towards the bottom of the file).  This master table must be referenced as the `currentTable` at the top of ***public/js/index.js***. 

Each item in the tables is represented by an Entry object.  We create new Entries with the command `new Entry( probability, 'text', subTable)`, where `probability` is an integer representing the likelihood of rolling that entry, `text` is the text that will be displayed when that entry is rolled, and `subTable` is an optional reference to another table that will be rolled on when that entry is selected.
The Multi object exists for when the sub-table is actually multiple sub-tables, for when we want to roll multiple items at once.  Multi is similar to Entry, except they have no probability, and the sub-table is not optional.  Examples for how to create a Multi object can be seen on line 95.  In this case, th

There are multiple arrays declared ( `const arrayName = []`) that represent individual tables. An array is normally represented as different variables separated by commas, like so (`[ 1 , secondItem, 'someText' ]`).  Here, we use the `push` function to declare new `Entry` objects and add them to the array.
