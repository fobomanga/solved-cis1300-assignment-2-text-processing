Download Link: https://assignmentchef.com/product/solved-cis1300-assignment-2-text-processing
<br>
<h1>Introduction</h1>




Text is a very important part of the data that computers deal with.  In this assignment you are going to learn two things: how to process text (the first step in understanding language) and how to write code in small, bite-size portions: functions!




<h1>Functionality</h1>




Once again you will write your programs in increasingly more powerful pieces.  But unlike the first assignment you will only produce two main programs and a number of functions.  The number of functions that you write correctly will determine your grade.




Remember the <strong>wcount.c</strong> program in the textbook and in class.  You will find a related program in the file <strong>textRW.c</strong>.  In the original program, the text was read in a character at a time.  The program <strong>textRW.c</strong> reads in text, one <strong><em>line</em></strong> at a time.  The program assumes that no line contains more than 500 characters.  Your code will not be tested on text that violates this constraint.




To test out <strong>textRW</strong> do the following:

$ make textRW $ cat verneTest.txt | ./textRW




Produce the following functions that will work on a single line of text:




<h2>int chop ( char *line )</h2>

<ul>

 <li>Remove the ‘
’ from the end of the line.</li>

 <li>Returns 0 if successful and -1 on failure.</li>

</ul>




<h2>int convertLowerCase ( char *line )</h2>

<ul>

 <li>Convert all alphabetic characters to lower case (do not use the tolower() function in the string library for C or your grade will be zero for this function).</li>

 <li>Returns the number of characters converted from upper case to lower case.</li>

</ul>




<h2>int replaceDigits ( char *line )</h2>

<ul>

 <li>Replace the all numbers/digits (0-9) with blanks.</li>

 <li>Returns the number of digits replaced with blanks.</li>

</ul>




<h2>int replacePunc ( char *line )</h2>

<ul>

 <li>Replace all punctuation and symbols with blanks. A list of all punctuation and symbols appears in the <strong>Information</strong> section of this assignment.</li>

 <li>Returns the number of punctuation and symbols replaced with blanks.</li>

</ul>




<h2>int reduceSpace ( char *line )</h2>

<ul>

 <li>Reduce all white space (blank characters and tabs to a single blank space).</li>

 <li>Returns the number of white spaces removed.</li>

</ul>




<h2>int trim ( char *line )</h2>

<ul>

 <li>Trim all white space from the beginning and from the end of each line.</li>

 <li>Returns 0 on success and -1 on failure.</li>

</ul>




Now compile the program <strong>findWords.c</strong> with your functions using <strong>Makefile</strong> and run this against the test file called <strong>verneTest.txt</strong>.




<h2>$ make findWords $ cat verneTest.txt | ./findWords</h2>




Your output should look like the output in file <strong>resultsVerne.txt</strong>.




The <strong>findWords</strong> program has found all the words in the file that are greater than <strong>5 characters</strong> in length.




Now run the following pipeline:




<h2>$ cat verneTest.txt | ./findWords | sort</h2>




The output should look like the output in file <strong>sortedResultsVerne.txt</strong>.




Your last task is to write a program called <strong>wordBag.c</strong> that prints out all the unique words produced by the previous pipeline with their counts (number of times that they occur).  The output will look like the output in file <strong>countsResultsVerne.txt</strong>.




Now run the following pipelines:




<h2>$ cat verneTest.txt | ./findWords | sort | ./wordBag  $ cat verneTest.txt | ./findWords | sort | ./wordBag | sort gk1,1r -gk2,2</h2>




Now you have a set of programs and functions that show you how popular specific words are in a text.




<strong>             </strong>

<strong>Information  </strong>ASCII Table – all punctuation and symbols are indicated in the blue boxes.

<u>http://www.asciitable.com/</u>