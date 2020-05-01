# ASP.NET-Core-Foreign-Keys
How to: Foreign Keys

<h2>Logic</h2>
Refer to following <b>ERD Relationships</b>: 
<ul>
  <li>One-to-One</li>
  <li>One-to-Many</li>
  <li>Many-to-Many</li>
  <li>Many-to-One</li>
</ul>
<br />

This is an extremely important step, so make sure the tables follow the appropriate relationships!

<h2>Model</h2>
<ol
  <li>Start by creating the table as per-normal.</li>
  <li>When setting the table 'ID', set the name as '[TABLE]ID'. This will ensure there are no conflicts when establishing the foreign key relationships between the tables.</li>
  <li><b>In the dependent table (child table)</b>, set a column name similar to the Parent table ID (i.e. Student > Course == StudentID or vice versa).</li>
  <li>Now, establish the connection between the Parent table by using 'public [TABLE_NAME] [TABLE_NAME] {get; set;}'. For example, public Course Course {get; set;}.</li>
  <li>This simply establishes the connection to the Parent table so that you aren't just referencing an out-of-the-blue value.</li>
  <li>Finally, add the Data Annotation '[ForeignKey("[PARENT_TABLE_ID]")]'. For example, [ForeignKey("CourseID")].</li>
  <li>Doing this links the Foreign Key from the Child table to the Parent table.</li>
</ol>

<!--
<h2>Views w/ Foreign Keys</h2>
If you haven't already scaffolded the models, do so now. Visual Studio will automagically generate the views with the foreign key controller logic. 
<br />
If you are working on an existing view and don't want to change anything in either the Controller or View, go to the respective Controller file and add the following changes:
<ol>
  <li></li>
</ol>
-->
<hr />
<h1>Self notes cause I'm a fucking rtard</h1>
<ul>
  <li>Make sure that in the Controller of said class model that the 'Bind[()]' section is a one-liner. DO NOT separate them into individual lines. Doing so will cause .NET to not detect the values on Create().</li>
  <li>Make sure to correctly include the linking database in the Independent table (i.e. .Include(d => d.[TABLE]).</li>
  <li>Ensure the 'ViewData' or 'ViewBag' temp data grabber method is done correctly. Incorrectly doing so will either throw a Null Object Reference error as you are attempting to grab a literally null object (one that is non-existent).</li>
  <li>Ensure that in the Models, the 'ForeignKey' data annotation is set correctly and references the correct column name (case sensitive).</li>
  <li>If getting an 'INSERT Statement...' error, it's very very likely that existing data is causing problems with the table. Either find a way to update/alter the existing table and add the 'null operational' tag (?) to the foreign key columns. Otherwise, last resort, you will need to delete all existing data relevant to the independent table.</li>
</ul>
