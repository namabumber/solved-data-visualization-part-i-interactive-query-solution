Download Link: https://assignmentchef.com/product/solved-data-visualization-part-i-interactive-query-solution
<br>
<h1>OVERVIEW</h1>

In this assignment, you are asked to design and develop a Data Visualization application to provide school administrators and students with a web-enabled interface to perform online query on school information, such information as course description, student GPA, course location, instructor name and so on; based on the responses from the users, the application then generates a SQL statement to fetch the data needed; based on the data returned from SQL server, the screen will be refreshed with the requested information shown in a tabular format or as graphical plot.  The application will be composed of 3 primary components: Graphical User Interface (GUI), SQL Interface and Graphical Tool depicted as follows:




<img decoding="async" data-recalc-dims="1" data-src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2019/09/266.png?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

 <noscript>

  <img decoding="async" src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2019/09/266.png?w=980&amp;ssl=1" data-recalc-dims="1">

 </noscript>



















The GUI component will be composed of 2 web pages, one for online course query and the other for statistical information on student GPA distribution.  The format of the query page is shown as follows:

Whereas the format of the statistics page is shown as follows:







SPECIAL SKILLS




<ul>

 <li>Data Visualization: using “Bokeh” to construct the web-based GUI to interface with the end users for online query</li>

 <li>Relationship Database: constructing simple SQL statements to extract the relevant information from a database.</li>

 <li>Using data visualization tool to turn raw data into interactive 2-D graphics such as lines, scatter plots, bar graphs, stacked bars and so on.</li>

 <li>Using ODBC to interface the SQL server</li>

 <li>Using widgets to capture user responses: text input, radio buttons, button groups, tables, dropdown list and so on.</li>

</ul>




<img decoding="async" data-recalc-dims="1" data-src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2019/09/352.png?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

 <noscript>

  <img decoding="async" src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2019/09/352.png?w=980&amp;ssl=1" data-recalc-dims="1">

 </noscript>




<h1><img decoding="async" data-recalc-dims="1" data-src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2019/09/789.png?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

 <noscript>

  <img decoding="async" src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2019/09/789.png?w=980&amp;ssl=1" data-recalc-dims="1">

 </noscript>COPE – TAB PANEL</h1>













<ol>

 <li>Using bokeh tool to construct a multi-tab panel for the home page:

  <ol>

   <li>First panel as “Course Info”</li>

   <li>Second panel as “Statistics”</li>

  </ol></li>

 <li>The panel “Course Info” holds the online course query page, refer to corresponding section for more details.</li>

 <li>The panel “Statistics” holds the statistics page, refer to corresponding section for more details.</li>

</ol>




<h1>COPE – COURSE INFO</h1>




<ol start="4">

 <li>Using bokeh widgets &amp; layout to construct the web-based interactive query screen.

  <ol>

   <li>refer to the given template file (ui.py) for information.</li>

  </ol></li>

 <li>The A-Z button group, when clicked, will display all courses with title beginning with the letter of the clicked button, the result will be displayed in the data table shown on the bottom of the screen.</li>

 <li>Two sets of “begin with ….”-“…contains…”-“…ends with” button-groups, one for the course title and the other for department name. They behave as radio buttons.  They are used together with the two corresponding text inputs, namely “Title” and “Department” respectively.

  <ol>

   <li>These 3 buttons indicate whether or not the given string will be used as prefix, infix or suffix match respectively. If “begins with…” is selected, courses will be matched with title beginning with the given text; if “…contains…” is selected, title containing the given text will be matched.</li>

   <li>Ex: “begin with…” with input “bio”, courses such as “biology”, “bioinformatics” are shown.</li>

  </ol></li>

 <li>The “and”-“or” radio button-group indicates whether or not to search on title and department as a group (“and”) or separately (“or”).</li>

 <li>When the button “Refresh” is clicked, the actual search will take place and the result will be displayed in the data table. The search is based on a database table called “lgu.course”.

  <ol>

   <li>sp_help “lgu.course” to view its structure (refer to session “Database – Info”)</li>

  </ol></li>

 <li>It is required that the program execute another SQL statement to fetch the whatever the data requested. It is NOT supposed to cache the entire course table in memory and avoid further database request.   Though the size of the course table for this exercise is small in size, however, in reality, it can be potentially large in size; it’s therefore best practice to use SQL query to fetch only the data needed.</li>

</ol>

Examples:










<ul>

 <li>“…contains…” with “bio” as Title and “finance” as Department, with “and” option</li>

 <li>“…contains…” with “bio” as Title and “finance” as Department, with “or” option</li>

</ul>




<h1>DATABASE – INFO</h1>




Using Visual Studio Code, create a file of type “sql”, make a database connection to “csc1002” and perform a query execution with the following statement:




<ul>

 <li>sp_help “lgu.course”</li>

</ul>




<ul>

 <li>ODBC connection string:</li>

</ul>




<h1>SCOPE – STATISTICS</h1>




<ol>

 <li>Using bokeh widgets &amp; layout to construct the web-based interactive query screen.

  <ol>

   <li>refer to the lab materials for more information</li>

  </ol></li>

 <li>On the right side of the page is a stacked bar chart, showing the GPA distribution by department, further categorized by class year.</li>

 <li>On the left side of the page is a selection list displaying the list of all departments

  <ol>

   <li>It is used to select the department for which the chart is created</li>

  </ol></li>

 <li>When a new department is selected, the chart will be updated to refresh the corresponding information.</li>

 <li>The stacked bar chart shows student GPA distribution based on the selected department.

  <ol>

   <li>Students are from class of 2015, 2016 &amp; 2017 (year)</li>

   <li>As illustrated, GPA counts are stacked in chronological order, each with a unique color</li>

   <li>Legend (upper right) is shown to display the color of the classes</li>

  </ol></li>

 <li>The database table to use is “lgu.student” and the structure is shown as follows:</li>

</ol>




<u>S</u><u>TARTUP </u><u>O</u><u>PTIONS</u>




“bokeh serve –show &lt;a2.py&gt;”




<h1>SKILLS – PYTHON</h1>




In this assignment, you will be trained on the use of the followings:




Standard Python Object:




<ul>

 <li>Use standard objects (strings, numbers &amp; lists)</li>

 <li>Control statements to interact with users</li>

 <li>Variable Scope</li>

 <li>String formatting (method style)</li>

 <li>Functions for program structure and decomposition</li>

</ul>










<h1>DELIVERABLES</h1>




<ol>

 <li>Design documentation (A2_School_StudentID_Design.doc/pdf)</li>

 <li>Program source code (A2_School_StudentID_Source.py)</li>

 <li>Output (A2_School_StudentID_Output.doc/pdf)</li>

</ol>




Zip all files above in a single file (A2_School_StudentID.zip) and submit the zip file by due date to the corresponding assignment folder under “Assignment (submission)”

For instances, a SME student with student ID “119010001”:

   A2_SME_119010001.zip:

o A2_SME_119010001_Design.doc/pdf o A2_SME_119010001_Source.py o A2_SME_119010001_Output.doc/pdf

5% will be deducted if any files are incorrectly named!!!




<h1>DESIGN DOCUMENTATION</h1>




For the design document provide write-up for the following information:

<ol>

 <li>Design:

  <ol>

   <li>Describe the general structure of the program (functions, variables and program flow).</li>

  </ol></li>

 <li>Test Plan:

  <ol>

   <li>Refer to assignment 1 for information.</li>

  </ol></li>

</ol>




<h1>TIPS &amp; HINTS</h1>




<ul>

 <li>For executing and debugging “bokeh”, refer to the uploaded file “launch.json” and “tasks.json”.</li>

 <li>For general information on “Bokeh”, refer to the following link: <u>https://bokeh.pydata.org/en/latest/docs/user_guide.html</u></li>

 <li>For adding widgets (text input, list box, button groups, tables ..etc), refer to the following link: <u>https://bokeh.pydata.org/en/latest/docs/user_guide/interaction/widgets.html</u>  For reference guide, refer to the following link: <u>https://bokeh.pydata.org/en/latest/docs/reference.html</u></li>

</ul>










<h1>DEBUGGING</h1>







<h1>VSC TASKS</h1>







Note: replace IP (20.20.12.68) with your own local IP.  5006 is the http port, do not need to change it.

<h1>SAMPLE OUTPUT</h1>







<h1>MARKING CRITERIA</h1>




<ul>

 <li>Coding Styles – layout, comments, white spaces, naming convention, variables, indentation.</li>

 <li>Documentation – Design + Test Plan</li>

 <li>Program Correctness – logic, program structure, functions with appropriate parameters</li>

 <li>User Interaction – how informative and accurate information is exchanged between game player and host.</li>

 <li>Readability counts – programs that are well structured and easy-to-follow using functions to breakdown complex problems into smaller cleaner generalized functions are preferred over a function embracing a complex logic with nested conditions and sub-functions! In other words, a design with clean architecture with high readability is the predilection for the course objectives over efficiency.</li>

 <li>KISS approach – Keep It Simple and Straightforward.</li>

 <li>Balance approach – you are not required to come up a very optimized solution. However, take a balance between readability and efficiency with good use of program constructs.</li>

</ul>







<u>C</u><u>HALLENGES</u>




Completed by due date


