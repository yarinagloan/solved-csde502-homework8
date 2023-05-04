Download Link: https://assignmentchef.com/product/solved-csde502-homework8
<br>
<em><strong>Explanation</strong></em>: This assignment is intended to give you more practice in manipulating variables.

<em><strong>Instructions</strong></em>:

<ol>

 <li>Make sure your Rmd file has no local file system dependencies (i.e., anyone should be able to recreate the output HTML using only the Rmd source file).</li>

 <li>Make a copy of this Rmd file and add answers below each question.</li>

 <li>Change the YAML header above to identify yourself and include contact information.</li>

 <li>For any tables or figures, include captions and cross-references and any other document automation methods as necessary.</li>

 <li>Make sure your output HTML file looks appealing to the reader.</li>

 <li>Upload the final Rmd to your github repository.</li>

 <li>Download <a href="../files/assn_08_id.txt">assn_08_id.txt</a> and include the URL to your Rmd file on github.com.</li>

 <li>Create a zip file from your copy of assn_08_id.txt and upload the zip file to the Canvas site for Assignment 8. <em><strong>The zip file should contain only the text file. Do not include any additional files in the zip file–everything should be able to run from the file you uploaded to github.com. Use zip format and not 7z or any other compression/archive format.</strong></em></li>

</ol>

<h1>1</h1>

Imagine a new variable: multirace, using the following value definitions:

1 = one race, White2 = one race, not White3 = two races, includes White4 = two races, both non-White5 = three or more races, includes White6 = three or more races, all non-White9 = any race missing (White, Black/African American, American Indian, Asian, other)

<h2>1.1</h2>

<strong>Fill in the codes for the hypothetical cases below (Table 1).</strong>

Table 1: A hypothetical data set

<table>

 <thead>

  <tr>

   <td><strong>white</strong></td>

   <td><strong>black</strong></td>

   <td><strong>AI</strong></td>

   <td><strong>asian</strong></td>

   <td><strong>raceother</strong></td>

   <td><strong>multirace</strong></td>

  </tr>

 </thead>

 <tbody>

  <tr>

   <td>1</td>

   <td>0</td>

   <td>0</td>

   <td>0</td>

   <td>0</td>

   <td>1</td>

  </tr>

  <tr>

   <td>0</td>

   <td>1</td>

   <td>0</td>

   <td>0</td>

   <td>0</td>

   <td>2</td>

  </tr>

  <tr>

   <td>1</td>

   <td>0</td>

   <td>0</td>

   <td>1</td>

   <td>0</td>

   <td>3</td>

  </tr>

  <tr>

   <td>0</td>

   <td>1</td>

   <td>1</td>

   <td>0</td>

   <td>0</td>

   <td>4</td>

  </tr>

  <tr>

   <td>1</td>

   <td>1</td>

   <td>0</td>

   <td>1</td>

   <td>0</td>

   <td>5</td>

  </tr>

  <tr>

   <td>0</td>

   <td>1</td>

   <td>0</td>

   <td>0</td>

   <td>1</td>

   <td>4</td>

  </tr>

  <tr>

   <td>0</td>

   <td>1</td>

   <td>1</td>

   <td>0</td>

   <td>1</td>

   <td>6</td>

  </tr>

  <tr>

   <td>1</td>

   <td>0</td>

   <td>1</td>

   <td>0</td>

   <td>0</td>

   <td>3</td>

  </tr>

  <tr>

   <td>1</td>

   <td>1</td>

   <td>1</td>

   <td>0</td>

   <td>1</td>

   <td>5</td>

  </tr>

  <tr>

   <td>6</td>

   <td>1</td>

   <td>8</td>

   <td>1</td>

   <td>6</td>

   <td>9</td>

  </tr>

 </tbody>

</table>

<h2>1.2</h2>

<strong>Using this data frame (code below), report how many cases checked more than one race.</strong> Use R code to make this calculation and use inline expressions.

dat &lt;- structure(    list(        white = c(1L, 0L, 1L, 0L, 1L, 0L, 0L, 1L, 1L, 6L),        black = c(0L, 1L, 0L, 1L, 1L, 1L, 1L, 0L, 1L, 1L),         AI = c(0L, 0L, 0L, 1L, 0L, 0L, 1L, 1L, 1L, 8L),         asian = c(0L, 0L, 1L, 0L, 1L, 0L, 0L, 0L, 0L, 1L),         raceother = c(0L, 0L, 0L, 0L, 0L, 1L, 1L, 0L, 1L, 6L),         multirace = c(NA, NA, NA, NA, NA, NA, NA, NA, NA, NA)    ),     class = “data.frame”,     row.names = c(NA, -10L))dat &lt;- structure(    list(        white = c(1L, 0L, 1L, 0L, 1L, 0L, 0L, 1L, 1L, 6L),        black = c(0L, 1L, 0L, 1L, 1L, 1L, 1L, 0L, 1L, 1L),         AI = c(0L, 0L, 0L, 1L, 0L, 0L, 1L, 1L, 1L, 8L),         asian = c(0L, 0L, 1L, 0L, 1L, 0L, 0L, 0L, 0L, 1L),         raceother = c(0L, 0L, 0L, 0L, 0L, 1L, 1L, 0L, 1L, 6L),         multirace = c(NA, NA, NA, NA, NA, NA, NA, NA, NA, NA)    ),     class = “data.frame”,     row.names = c(NA, -10L)) dat &lt;- dat %&gt;%  mutate(multirace = rowSums(across(white:raceother)))

There are 8 cases that checked more than one race in this data frame.




<h2>1.3</h2>

<strong>Write R code to create the multirace variable, using the data set <a href="../data/AHwave1_v3.rds">AHwave1_v3.rds</a>.</strong> <em>Hint: You may want to create another variable, numrace, that counts the number of races.</em> Use <a href="https://stat.ethz.ch/R-manual/R-devel/library/utils/html/download.file.html">download_file()</a> and Sys.getenv(“TEMP”) to download the file to your system’s TEMP directory to avoid local file system dependencies.

<h2>1.4</h2>

<strong>Label the multirace variable as well as its values using attribute labels.</strong> Include the code here.

<h2>1.5</h2>

<strong>Include below a contingency table of the multirace variable. Make sure that the values are labelled so the table is readable, and also include any missing values.</strong>

<h1>2</h1>

<strong>Review part B of each of the answers (i.e., </strong><strong>H1KQ1B .. H1KQ10B</strong><strong>) to the Knowledge Quiz (Section 19 of the Add Health questionnaire, documented in </strong><strong>INH19PUB.PDF</strong><strong>). The 10 questions each ask: â€œHow confident are you that your answer is correct?â€</strong>

<h2>2.1</h2>

<strong>Write R code that creates a single summary variable named </strong><strong>kqconfidence</strong><strong>, with a larger number representing the respondent being more confident across all questions (scale of 0 to 3 for each individual question; </strong><strong>kqconfidence</strong><strong> will be the sum for each subject across the 10 questions). Note that any observations with value 7 (i.e., age less than 15) should be removed from the data frame, and values 6, 8, and 9 should be coded as </strong><strong>NA</strong><strong> (i.e., missing) for the purposes of scoring confidence. Document your code so that the reader knows how you scored the scale and how you handled missing values. Make sure to label the new variable.</strong>

<h2>2.2</h2>

<strong>Create and include below a contingency table from kqconfidence with raw counts, percentages, and cumulative percentages. Put code to do this in your .R file.</strong>

<h2>2.3</h2>

<strong>[BONUS] For each subject there were zero to 10 â€œmissingâ€ answers to each of the 10 component questions. We would like to know what this distribution is. Include below a table that shows the count of subjects for each unique value of the count of missing questions, and include code in your .R file.</strong>

<h2>2.4</h2>

<strong>For each possible value of the Knowledge Quiz Part A score (from Assignment 3), what is the mean kqconfidence level? (Include results below.)</strong>

<h2>2.5</h2>

<strong>[BONUS] For each respondent, create two different confidence scores: a confidence score for the items answered correctly and a confidence score for the items answered incorrectly. How many respondents are more confident when answering incorrectly</strong>