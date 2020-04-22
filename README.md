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
