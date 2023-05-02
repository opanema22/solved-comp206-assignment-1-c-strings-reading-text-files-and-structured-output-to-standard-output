Download Link: https://assignmentchef.com/product/solved-comp206-assignment-1-c-strings-reading-text-files-and-structured-output-to-standard-output
<br>



Gain our first hands-on experience with coding software system specifications in C. Specific focus on working with C strings, reading text files and structured output to standard output.

Instructions:

Write the two C programs specified in the following questions. Test them very carefully and pay careful attention to detail, as marking will ensure that you program meets the specifications very precisely. Every program you submit must compile with “gcc program_name” on mimi.cs.mcgill.ca without errors or warnings. When run with the examples shown here, as well as additional correct inputs, the corresponding correct output must be generated. If run with incorrect inputs, the program must never crash (segfault, bus error, etc),but rather print informative errors and exit cleanly.

Automated Testing:

The eval.py script contained in the assignment folder can be used to ensure your program works well with our automated grading. It will compile run several of the basic tests and report the results. To run it, place your C files in a folder, and run “$ python &lt;folder_name&gt;”. You will see a fairly long report generated. When everything works, you should see the string “Your program’s output is the same as expected output: True” for both questions. This is similar to the process we’ll use for real grading, but that will include a wider range of test cases, so do run your program directly yourself and ensure it always works!

Handing In:

Upon completion, create an archive file with both your C programs using the command:

$ tar –czf A1_submission.tar.gz q1_julia_explorer.c q2_calendar.c

Submit the resulting archive on My Courses.

Due Date:

<ol>

 <li>For full marks: Friday Feb 9<sup>th</sup></li>

 <li>Final deadline (with 10% penalty): Tuesday Feb 13th</li>

</ol>

Question #1 – Explore the Julia Sets (40 marks)

A <u><a href="https://en.wikipedia.org/wiki/Julia_set">Julia Set</a></u> is a construction from complex math that can be used to generate a wide range of fractal patterns, with the chaotic property: very small changes in the initial conditions lead to dramatic changes in the generated shape. A standard Linux tool, gnuplot, is capable of plotting a Julia Set from a simple text script and we have provided you with the basis of this script as the attached file “shape_template.txt”.

You will create a C program to automate the process of inserting the initial conditions, two floating point numbers, into the correct place in the script, a simple token replacement. In case you try this on your own computer, the command “sudo apt-get install gnuplot-x11” is likely to be helpful.

Write a program <strong>q1_julia_explorer.c </strong>that allows the user to produce Julia Set plots interactively:

<ol>

 <li>Accept exactly three command-line arguments &lt;file_path&gt; &lt;a&gt; &lt;b&gt;:</li>

 <li>&lt;file_path&gt;: A path to the provided “shape_template.txt” gnuplot script

  <ol>

   <li>Identify a correct shape_template.txt file as one your program can open for reading, and which contains two “tags”: #A# and #B#. For any incorrect file, output “Error: bad file” and return with code –1.</li>

  </ol></li>

 <li>&lt;a&gt;: A floating point value <strong>a</strong> (which has meaning in the construction of the Juliaset)</li>

 <li>&lt;b&gt;: A floating point value <strong>b</strong> (which has meaning in the construction of the Juliaset)</li>

 <li>For any problem with the a or b arguments, output “Error: bad float arg” and return –1 2. Produce a modified gnuplot script on standard out, where the modifications are exactly:</li>

</ol>

<table width="0">

 <tbody>

  <tr>

   <td rowspan="2" width="488"><strong> </strong></td>

   <td rowspan="2" width="7"><strong> </strong></td>

   <td width="156"></td>

   <td width="68"><strong> </strong></td>

  </tr>

  <tr>

   <td width="156"></td>

   <td width="68"><strong> </strong></td>

  </tr>

 </tbody>

</table>

<ol>

 <li>The #A# tag text is replaced with <strong>a</strong>, printed with 6 decimals (use %.6f)</li>

 <li>The #B# tag text is replaced with <strong>b</strong>, printed with 6 decimals (use %.6f)</li>

 <li>Note that the provided shape_template.txt is only an example. Your code should definitely handle the tags in this file, but hardcode as little about it as possible, such that any other file with the same tags can also be used for testing.</li>

</ol>

Examples test runs:




Question #2 – Formatting the year (60 marks)

Write a C program named <strong>q2_calendar.c</strong> that prints one year’s full calendar to standard output.

<ol>

 <li>Accept exactly 2 command-line arguments that control the calendar details:</li>

 <li>Maximum number of characters <strong>DAYSIZE </strong>to print for the day-of-week labels, which must be 2 or greater</li>

 <li>The day-of-week that starts the year <strong>FIRSTDAY</strong> as an integer from 1 to 7 (1 is Sunday in English)</li>

</ol>

<ol start="2">

 <li>Your output must precisely follow the <strong>format specification </strong>given by the following examples, so you should make sure you can replicate them precisely. Note that the examples were cut off at April only because we ran out of space on the page. The output must continue until Dec 30<sup>th</sup>. The full text specification of this format is on the next page.</li>

</ol>

<table width="0">

 <tbody>

  <tr>

   <td width="234"><strong> </strong></td>

   <td width="390"><strong> </strong></td>

  </tr>

 </tbody>

</table>




Detailed calendar specification:

<ol>

 <li>Accept exactly 2 command-line arguments:

  <ol>

   <li>Maximum number of characters <strong>DAYSIZE </strong>to print for the day-of-week labels, which must be 2 or greater</li>

   <li>The day-of-week that starts the year <strong>FIRSTDAY</strong> as an integer from 1 to 7 (1 is Sunday in English)</li>

   <li>Your output must precisely follow this specification (and shown in the examples below) for printing a year’s calendar.</li>

   <li>Every row must begin and end with the one pipe symbol “|”</li>

   <li>Each row contains (<strong>DAYSIZE+3) x 7 + 1 </strong>visible symbols, and a newline</li>

   <li>Each month is composed of:

    <ol>

     <li>A full-wdith <strong>separator line </strong>of dashes “-“</li>

     <li>A line composed of the month’s full name, centered using spaces, with one less space before than after if needed</li>

    </ol></li>

  </ol></li>

</ol>

<ul>

 <li>A <strong>separator line </strong></li>

</ul>

<ol>

 <li>A line with 7 columns of day labels, with pipes “|” in between. Each day label contains: i. A single space

  <ol>

   <li>The day-of-week name cut down to <strong>DAYSIZE </strong>characters if needed</li>

  </ol></li>

</ol>

<ul>

 <li>Additional spaces to pad up to <strong>DAYSIZE </strong>if needed A single space</li>

</ul>

<ol>

 <li>A <strong>separator line</strong></li>

 <li>5 or 6 lines that contain the days of that month:

  <ol>

   <li>Print exactly 30 days always (avoids leap-years etc). Separate day sections with pipes “|” in between</li>

  </ol></li>

</ol>

iii. Lay out the date numbers with the usual logic:

<ol>

 <li>The first day of Junuary is specified with the argument <strong>FIRSTDAY</strong></li>

 <li>The first day of each other month is on the weekday following the last weekday of the previous month</li>

 <li>When a week is not “full” with dates, blank days are printed to maintain spacing, both at the start and end of the month</li>

</ol>

<ol>

 <li>Each non-empty day section must contain, in order:

  <ol>

   <li>A single space</li>

   <li>The date as a one or two digit integer, following correct ordering</li>

  </ol></li>

</ol>

<ul>

 <li>Additional spaces to pad up to <strong>DAYSIZE </strong>if the number was too short A single space</li>

</ul>

<ol>

 <li>The final line of the year must be a <strong>separator line</strong></li>

</ol>





