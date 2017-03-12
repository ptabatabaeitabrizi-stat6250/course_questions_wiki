# Course Questions Wiki

This document contains questions and answers corresponding to reading from the course textbook.

To contribute,

1. fork this repo to your GitHub Account (e.g., using the "Fork" button in the upper-right-hand corner of the GitHub web interface),

2. make appropriate changes/corrections using Markdown (see https://guides.github.com/features/mastering-markdown/), and

3. initiate a pull request using

- the master branch of the stat6250/course_questions_wiki repo as the base fork and

- your version of the repo as the head fork.

The instructor will then review the pull request and make comments should further revision be needed. Then, after the contents of the pull request have been finalized without any merge conflicts, the instructor will merge the pull request.

********************************************************************************

## Chapter 1 Questions

[Chapter 1, Problem 1]
- Question (SK): Is indentation  crucial in SAS or it is just for readability? If not then why does some programs gives error because of wrong indentation?
- Answer (SK): Writing codes with proper indent is a best practice for programming.

- Question (WF): Does SAS make the distinction between a variable and an array?
- Answer (WF): array is a set of variables grouped together for the duration of a data step by being given a name in an ARRAY statement.

- Question (WF): Is it possible to have a completely empty observation? Would there be any reason to allow this?
- Answer (WF): It’s possible to create an empty dataset by stopping process before output.
    
- Question (AS): Is there a way to print out the values of certain variables during debugging i.e. equivalent of a print statement?
- Answer: TBD

\[Chapter 1, Problem 3\]
- Question (WF): Can a variable's type be both character and numeric?
- Answer (WF): No, a variable can be numeric or character. Numeric values represent numbers, can be read in a variety of ways, and are stored in floating-point format. Character values can contain letters, numbers, and special characters and can be from 1 to 32,767 characters long.

- Question (WF): Are there traditional variables found in SAS, variables without attributes?
- Answer (WF): all variables have its own attributes.

- Question (WF): In this problem, AcctNum appears like it should be set to a numeric type. What must be done to update it's type and correct the values? The first two need their underscores removed.'Romano' and 'Choi' are names, not account numbers.
- Answer (WF): Once a variable is defined numeric or character, you cannot change it's data type, you must create a new variable.

\[Chapter 1, Problem 5\]
- Question (WF): Is there a maximum length for variables?
- Answer (WF): default is 8 bytes for numeric and character.

\[Chapter 1, Problem 8\]
- Question (WF): Why was 8 bytes chosen? Is it efficient to store all variables with such a large precision?
- Answer (WF): 8 bytes is 64bits, which most CPUs today are 64-bit architecture.
- Question (AP):Can we configure the default length for the variable types? How?
- Answer(AP):We can configure the default length for variables using the length statement. General format is LENGTH variable-list $ number-of-bytes;

## Chapter 2 Questions

\[Chapter 2, Problem 3\]
- Question (WF): Is a file format engine a type of dataset?
- Answer (WF): A library engine is an engine that accesses groups of files and puts them into a logical form for processing by SAS. It’s a set of code and instruction.

- Question (WF): With 4 digit year values in data lines to be read correctly, does it mean that the YEARCUTOFF=option can be eliminated in the program data lines?
- Answer (WF): yes.

- Question (AS): Does YEACUTOFF= option also affect how data is interpreted while writing into and creating a new
   data set or only while reading in from an existing data set ?
- Answer: TBD

\[Chapter 2, Problem 7\]
- Question (IL): What's the difference between starting a SAS program with "data" versus "proc", and why do both end types of programs end with the same "run" command, even though the bodies of the programs look nothing alike?
- Answer (IL): SAS programs are divided into "steps", each step is either a data step or a proc step (as determined by the first word in the step), and all steps are typically terminated by a "run" statement. However, when using a "cards" or "dataline" statement in a data step, then the data step is terminated by a closing semicolon. In addition, some procs (like the interactive proc glm) are only terminated with a "quit" statement.
- Question(AP):What are the kinds of statements that should go in the data and proc components of the SAS program?
- Answer(AP): DATA step: Used to put external data into SAS data sets, create new data sets by merging, subsetting external data sets, compute values and check and correct errors in external data sets; PROC step: Analyse and process data from the sas data set, create reports, produce descriptive statistics etc

\[Chapter 2, Problem 8\]
- Question (WF): How are namespace conflict issues resolved when two libraries are needed which have the same naming naming conventions and same names?
- Answer (WF): SAS won’t allow to create or move a library at a location that has an existing library with the same name.

- Question (WF): If a data set with two-digit year values has the range of the year more than 100, how to set YEARCUTOFF= value? how to process the year correctly?
- Answer (WF): The YEARCUTOFF= option cannot reliably assign centuries to two-digit years if the range of dates for a variable is greater than 100 years. If the date ranges for a variable span more than 100 years, you must either specify the dates with 4-digit years, or use DATA step logic to assign a century to each year (perhaps based on the value of another variable).

\[Chapter 2, Problem 9\]
- Question (IL): What is a "libref", and how does it differ from a "LIBNAME"?  In particular, what fundamental distinction causes one to be written out in lower-case letters and the other in upper-case letters?
- Answer (SG): A libname statement is the syntactical statement used to initiate a particular library. The libref is the actual syntax used to name it.
- Question (AS): Can one sas library(folder) contain both SAS native format and external file types ? Does SAS automatically determine if/when to use the extra 'engine' parameter in the libname statement to use for reading the non-SAS file ?
- Answer: TBD
- Question (AS): what statement is used to delete a libref within a SAS program? opposite of LIBNAME?
- Answer: TBD
- Question (WF):  How to reference a library which is also a data file? for example, libname rptdata spss 'g:\\myspss.spss';
- Answer (WF): libname xdb excel "c:\\mymachine\\pcfdata\\demo.xlsx";
- Question (SK): What is YEARCUTOFF= option? Why is this different in two year and four year naming conventions?
- Answer (SK): The value of the YEARCUTOFF= system option affects only two-digit year values. A date value that contains a four-digit year value will be interpreted correctly even if it does not fall within the 100-year span set by the YEARCUTOFF= system option.
- Question (WF): What is a libref? Can a libref be within a DATA, SET, or PROC statement?
- Answer (WF): To create a new SAS library with SAS code, you use the LIBNAME statement. The LIBNAME statement associates the name of the library, or libref, with the physical location of the library. LIBNAME statement can be executed in bot DATA or PROC step.
- Question (WF): Can I name a library with some key words like SPSS? 
- Answer (WF): SAS reserves a few names for automatic variables and variable lists, SAS data sets, and librefs, such as WORK, SASHELPER, SASUSER...

## Chapter 3 Questions
[Chapter 3, General Questions]
- Question (AS): Is there a way to print out the values of certain variables during debugging i.e. equivalent of a print statement?
- Answer: TBD

\[Chapter 3, Problem 1\]
- Question (WF): Can DATA and PROC steps begin somewhere else other than column one? How about the RUN statement?
- Answer (WF): SAS programs include two types of steps: DATA steps and PROC steps. DATA steps begin with the keyword DATA, and PROC steps begin with the keyword PROC. Therefore, DATA and PROC steps begin in column one.

\[Chapter 3, Problem 3\]
- Question (WF): When syntax errors like unbalanced quotation marks are in a program, can quotation marks be added and resubmit the program to fix the error?
- Answer (WF): Yes, SAS program can be run or re-run by selecting a block of codes.

- Question (WF): if we use "sum" command, does the "fee" have to be defined in the variable section? 
- Answer (WF): “fee” is a variable in dataset clinic.stress.

- Question (WF): What are some errors that SAS can correct automatically? 
- Answer (WF): SAS does not correct error automatically, it find error for you.

- Question (AP):The error continues to occur in other SAS programs if the statement is not canceled(unclosed quotation marks). So, when we find such errors in the log window how do we make sure it of the current SAS program and not some other program from the session
- Answer(AP): Cancel all SAS statements, correct the error and run the SAS program again.

\[Chapter 3, Question 5\]
- Question (WF): what happens if the data values are not appropriate for the SAS statements? Is there a way to convert the data? 
- Answer (WF): SAS would write error message in the SAS log. You cannot convert variable data type.

- Question (WF): what would happen if the elements were right but not valid for that usage? 
- Answer (WF): You might be encountering run-time errors or getting wrong results.

- Question (WF): what does it look like to have program statements that are not conformed to the rules of the SAS language?
- Answer (WF): You would get syntax error.

- Question (SK): What is the way to figure out,where the logic error is and how can we rectify it without knowing the error log?
- Answer (PT): Logic eeror is the most difficult to debug, mainly becuase it needs a good knowldge of both programming and logics!! what I found super helpful is to replace statments with wither true and false results, and then do a rolle up of all the results. Basically, besides breaking a code into smaller sections and tackling each, there isnt any other easy way to solve Logic Errors. 
\[Chapter 3, Problem 7\]
- Question (WF): What do you do to fix misspelled words in SAS statements?
- Answer (WF): SAS is statistics, not word processing. You need to use an external spellchecker.

## Chapter 4 Questions
[Chapter 4, Problem 7]
- Question (AS): In this example, SAS continues to print even though sort fails. Is there a way to force SAS to halt processing if any intermediate steps fail ?
- Answer: TBD

\[Chapter 4, Problem 1\]

- Question (WF): Are English date formats the only formats SAS processes/produces? 
- Answer (WF): No, you can use “OPTIONS DATESTYLE=mdy; “ (or YDM, or YMD, or DMY…) to change date format.

- Question (WF): When do we want to make a label instead of just using them as a variable? Is it when for the convenience of the variables?
- Answer (WF): Using a LABEL statement in a DATA step permanently associates labels with variables by affecting the descriptor information of the SAS data set that contains the variables. 

\[Chapter 4, Problem 4\]
- Question (WF): If you specify the same out=ref.name in your procs does it overwrite the previous values in that SAS data object? 
- Answer (WF): Yes.

- Question (WF): What to do when you have more than one variable to be sorted? Does it still through the BY statement?
- Answer (WF):
```SAS
    PROC SORT statement option:
        OUT=
    BY statement
```
\[Chapter 4, Problem 7\]
- Question (WF): Must you always have a data out in the proc signature? 
- Answer (WF): The PROC Step or Procedure Step processes one (or more) data set(s) in some way to produce a result. This step is one of two types of SAS program steps, the other being a DATA Step, both are fundamental components of the SAS Language.

\[Chapter 4, Problem 10\]
- Question (WF): what’s to do if we want to remove columns or rows for the table that is not sorted through frequency?
- Answer (WF): To remove observations in SAS, you can use the IF statement in a DATA step, search and remove matched observation. 

- Question (WF): Can you specify triple spacing or more within the proc print statement?
- Answer (WF): No, there is an only double space.

- Question(BP): Can PROC PRINT default be changed for a session?
- Answer(BP):DATA and PROC statements signal the beginning of a new step. When SAS encounters a subsequent DATA, PROC, or RUN statement (for DATA steps and most procedures) or a QUIT statement (for some procedures), SAS stops reading statements and executes the previous step in the program. In our sample program, each step ends with a RUN statement.
- Question(BP): Does Data step statement produces output after executing Data step statement?
- Answer(BP) When the program is processed, it creates the SAS data set. The DATA step produces messages in the SAS log, but it does not create a report or other output.

## Chapter 5 Questions
\[Chapter 5, Problem 1\]
-   Question (WF): Why the format here is ".dat"?
-   Answer (WF): “dat” file extension here only indicates that’s a data
    file, it can be text or csv.
    
\[Chapter 5, Problem 2\]
-   Question (WF): Once a fileref is assigned to an external file, can
    the fileref be saved and utilized in other SAS sessions? 
-   Answer (WF): File Shortcuts are active only during the current
    SAS session. 
    
\[Chapter 5, Problem 6\]
-   Question (WF): Where to define the name/position for Infile command?
-   Answer (WF): The FILENAME option defines a variable, whose name you
    supply, that SAS sets to the value of the physical name of the
    currently open input data set.
   
[Chapter 5, Problem 7]
- Question (AS): How to read a raw data set in which each observation's data values are on two lines?
- Answer (AS): SAS provides the slash (/) and #n to handle cases where more than one record in the input file is required to compose one observation in the dataset. When SAS encounters a slash, it continues to read values till end of Input statement. Then writes the PDV out as one observation. The slash is a relative line pointer and #n is a specifc line pointer.
- Question (SK): Is there a way we can change the columns name and its size once we defined them ? How can we delete a column or reduce its size?
- Answer (IW): To delete a column in the SAS output, use *DROP* in the data option:
```SAS
        data sales_new(drop=store_inventory);
            set sales_old;
        run;
```
Alternatively, to delete any variable in a *DROP* statement within the DATA statement:.
```SAS
        data sales_new;
            set sales_old;
            drop store_inventory;
        run;
```
To modify column name, use a *RENAME* statment:
 ```SAS
        data sales_new;
            set sales_old;
            rename store_inventory = total_inventory;
        run;
```

Then to modify the column size, use a *PROC SQL* statement:
 ```SAS
        proc sql;
         alter table sql.sales_new;
            modify total_inventory int(5);
        quit;
```
-   Question (WF): Why is StockNumber read in as a character instead of
    a numeric type?
-   Answer (WF): Stock Number is a name, not a numeric value that
    requires calculation.
    
-   Question (WF): With the Price variable, can a $ be used to identify
    the variable?
-   Answer (WF): Numeric variable can only contain number(s), not any
    other character.
    
-   Question (WF): Would the "data" and "run" portions of the statement
    also need to be included for this to run properly or is it complete
    on its own?
-   Answer (WF): The RUN statement is the last statement in a DATA
    Step and indicates to SAS that the step is complete and can now be
    run.\[Ch 5, Q8\]

-   Question (WF): How would you create a new variable and then subset
    based off of that variable? Is it possible to do in one data block?
-   Answer (WF):
```SAS 
        DATA auto;
                INPUT make $ price mpg foreign;
            DATALINES;
            AMC 4099 22 0
            Audi 6295 23 1
            ; 
                set import;
                where foreign = ‘1’
            run;
```

## Chapter 6 Questions
\[Chapter 6, Problem 1\]
-   Question (WF): What is the size of the input buffer?
-   Answer (WF): The default input buffer size on Windows is 256 bytes.

\[Chapter 6, Problem 2\]
- Question (WF): Since incorrect values and formats are not considered syntax errors, how can they best be detected and fixed?
- Answer (WF): Semantic Errors shows in the SAS log window, and <span id="z1377902" class="anchor"></span>you can use system options to control error handling (resolve errors) in your program.

- Question (WF): what does it look like in SAS execution step when there is incorrect values and formates?
- Answer (WF): SAS skids the wrong codes and write error to SAS log.

\[Chapter 6, Problem 3\]
- Question (AS): What are the additional commands used to direct the DATA step not to execute for each record? What are the conditions in which we need to use such commands and what are the advantages? Can we give an example?
- Answer (AS): Each iteration of a data step reads in data from the input file into the buffer,  the input statement writes it into the program data vector, and  at the end of the DATA step,SAS writes teh PDV contents out into the result dataset. Sometimes, you may need to test some conditions for selecting what observations get written out into teh result dataset. Based on an IF condition, The DELETE statement can be used to stop processing current iteration of data step and return to the beginning of the data step so that teh row is not written out to the result dataset.                  

- Question (WF): What type of statement is used for the data step to execute more than once for each record in the input file?
- Answer (WF): using \# to move pointer to different row of in the group, for example:

```SAS

        INPUT
        #1 row1 2. data1 $7. @11 ar1 1.
        #2 row2 2. data2 $7. @11 ar2 1.
```
\[Chapter 6, Problem 4\]
- Question (WF): At the beginning of the execution phase, can the value \_N\_  and \_ERROR\_ be different than the default value?
- Answer (WF): \_N\_<span id="a001375305" class="anchor"></span>is initially set to 1. Each time the DATA step loops past the DATA statement, the variable \_N\_ increments by 1. The value of \_N\_ represents the number of times the DATA step has iterated.<span id="a001375306" class="anchor"></span> \_ERROR\_<span id="a001375307" class="anchor"></span>is 0 by default but is set to 1 whenever an error is encountered, such as an input data error, a conversion error, or a math error, as in division by 0 or a floating point overflow. You can use the value of this variable to help locate errors in data records and to print an error message to the SAS log.

\[Ch 6, Q5\]
- Question (WF): Is it possible to sum up the total \_ERROR\_ count
    for a summary statistic?
- Answer (WF): \_*ERROR*\_ is a binary automatic variable, you need to
    write additional codes to sum up .
    
[Chapter 6 , Problem 6]
- Question (SK): When does LINES or CARDS  statements are used in the last statement of a data step ? when both are alias of   DATALINE statement?
- Answer: TBD

- Question (WF): Why is it so important that the variables initially be set to missing?
- Answer (WF): SAS must have some character to display for missing, it won't allow no character.



[Chapter 6, Problem 7]
- Question (AS): typically, is the metadata related to the position of the columns in data file provided/available ? Would it not be tedious to create the input statement for datasets with large number of attributes? Are there any general purpose utilities available to do this task of parsing sample data to create input statements ?
- Answer: TBD


## Chapter 7 Questions

[Chapter 7 ,Problem 7]
- Question (SK): Need to see an example using "OTHER" for missing numeric values in a proc format step?
- Answer (IW): The *OTHER* includes all ages not listed in teams 20 & below and between 20 to 40, and all missing ages, unless missing values are accounted for with . = 'Missing'.
```SAS
	proc format;
  		value age 
			low -< 20 = "team 1"
			21 -< 40 = "team 2"
			other = "undefined";
	run;
```


\[Chapter 7, Problem 3\]
- Question (WF): How can SAS version 9 and above be backwards compatible if format-names may now be up to 32 characters?
- Answer (WF): SAS version prior 9 support format names up to 8 characters, and the version 9 supports format names up to 32. “Up to” means any number between 1 to 32.

- Question (WF): Is it necessary to establish a catalog for formats in the library? Or is that not necessary when using a value statement?
- Answer (WF): Not necessary. If you plan to use a customized informat or format repeatedly, you can store it permanently in a "formats catalog" by using the LIBRARY= option in the PROC FORMAT statement. Basically, the LIBRARY= option tells SAS where the formats catalog is (to be) stored.

\[Chapter 7, Problem 4\]
- Question (WF): Why is a library.catalog not used here?
- Answer (WF): LIBRARY=libref names the library that the procedure processes. This library is the procedure input library.

- Question (WF): Creating value/name pairs is it possible to lookup values by label name?
- Answer (WF): Labels can be used to improve both the efficiency and quality of the SAS output. It’s not designed for value searching.

\[Chapter 7, Problem 6\]
- Question (WF): Why are labels unrestricted in size (i.e. relatively so) when compared to SAS variable lengths?
- Answer (WF): Label add value to the user and make it more efficient and flexible to program. It’s not designed to hold value.

\[Chapter 7, Problem 7\]
- Question (WF): Is there a single one place where one can go to have the equivalent of a 'JavaDoc' for SAS?
- Answer (WF): DocItOut (formerly SASDoc).

\[Chapter 7, Question 8\]
- Question (WF): What happens if place FORMAT statement in a PROC step?
- Answer (WF): You can put a format statement in a proc step so that the variable has a different format for the output you produce in the proc step. This will not change the format of the variable in the dataset.

## Chapter 8 Questions

\[Chapter 8, Problem 1\]
- Question (WF): Is it possible to create a stem-leaf display? 
- Answer (WF): Using The PROC UNIVARIATE statement.

- Question (WF): Does the raw data need to be totally clean before performing PROC statements?
- Answer (WF): No PROC step can also take actions when errors occur, but it is highly recommended to clean up data set in DATA step.

[Chapter 8, Problem 2]
- Question (AS): there is also statistic named 'VAR' for variance ? does this cause SAS issues ?
- Answer: TBD

\[Chapter 8, Problem 4\]
- Question (WF): Is there any difference in the data output that would make either CLASS or BY a better choice, or is it simply a matter of ease and organization?
- Answer (WF): The input dataset must be sorted by the BY variables. It doesn't have to be sorted by the CLASS variables. The MEANS procedure is more efficient at treating BY groups than CLASS groups.

- Question (WF): When using BY with PROC SUMMARY should SORT need to be used first as well?
- Answer (WF): Yes.

\[Chapter 8, Problem 7\]
- Question (WF): How do you return a single ratio value from the sum of two columns? 
- Answer (WF):

```SAS
    DATA have;
         input COL1 COL2;
    DATALINE;
    2 4
    5 6
    ;
     run;
    PROC SORT data=have; 
        by COL1; 
    run;
    PROC MEAN data=have noprint;
        by COL1;
    output ratio=COL1/(COL1+COL2) out=want (drop = \_type\_ \_freq\_);
     run;
    proc print data=want;
    run;
```

- Question (SK): what is the default output of frequency procedure?
- Answer (SK): The FREQ procedure is a descriptive procedure as well as a statistical procedure. It produces one-way and n-way frequency tables, and it concisely describes your data by reporting the distribution of variable values. You can use the FREQ procedure to create crosstabulation tables that summarize data for two or more categorical variables by showing the number of observations for each combination of variable values.

- Question (AS): in relation to proc frequency, what are 'categorical values' ?
- Answer: TBD

\[Chapter 8, Problem 8\]
- Question (WF): What's the best way to work on continuous values, numeric values and unique values? Maybe to sort the data first before perform the frequency distribution? 
- Answer (WF): Recommended. By using PROC SORT, you can also do things like create a new data set, subset your data, rename, drop, keep, format, or label your variables all in that same procedure.

\[Chapter 8, problem 10\]
- Question (WF): Does memory can impact when we use multiple PROC freq command to generate cross-tabulations.
- Answer (WF): Yes, The system option MEMSIZE sets a limit on the amount of memory used by the SAS System. The memory size impact SAS program performance in general.

- Question (SK): Does reversing the order of the variables in the TABLES statement would reverse their positions in the table?
- Answer: TBD  

## Chapter 10 Questions

\[Chapter 10, Problem 2\]
- Question (WF): Is it always true proc formats and labels will trump labels and formats defined in data steps?
- Answer (WF): SAS program is executed in sequential order.

\[Chapter 10, Problem 7\]
- Question (WF): What does it do with the DATA step for the length of the variable? When to use the LENGTH statement?
- Answer (WF): The LENGTH function returns an integer that represents the position of the rightmost non-blank character in string. If the value of string is blank, LENGTH returns a value of 1.

- Question (WF): How does the code look like if we write it out with different ways?
- Answer (WF):
```SAS
	len=length('ABCDEF');
	put len;
```
\[Chapter 10, Problem 8\]
- Question (WF): Are SELECT groups like case and switch statements in other programming languages?
- Answer (WF): Yes, C++, Java, Python.

- Question (WF): The problem code requires both IF..THEN statements to run irrespective of they being true, so why isn't option 2 correct (ELSE statement will get executed only when the IF statement is false)?
- Answer (WF): IF THEN statement only specifies one condition, the ELSE statement specified all other conditions.

- Question (WF): Are the values deleted using the IF..THEN DELETE statement permanently deleted from the data set?
- Answer (WF): Use the DELETE statement when it is easier to specify a condition that excludes observations from the data set or when there is no need to continue processing the DATA step statements for the current observation. To actually delete the records and renumber the remaining observations, use the PURGE statement.

\[Chapter 10, Question 9\]
- Question (WF): How to rewrite the length statement so that the program can run successfully?
- Answer (WF):
```SAS
	length s $ 5;
	s=’ab ’;
	l=length(s);
	put ’L=’l;
	
```
## Chapter 11 Questions

\[Chapter 11, Problem 1\]

- Question (WF): What happens if there was no subset data, the DROP= and KEEP= options are switched in the DATA/SET statements, and variable "weight" has been eliminated?
- Answer (WF): The** DROP=** option tells SAS which variables you want to *drop from* a data set. If you place the **DROP=** option on the SET statement, SAS drops the specified variables when it reads the input data set. On the other hand, if you place the **DROP=** option on the DATA statement, SAS drops the specified variables when it writes to the output data set. The** KEEP=** option tells SAS which variables you want to *keep in* a data set. If you place the **KEEP=** option on the SET statement, SAS keeps the specified variables when it reads the input data set. On the other hand, if you place the **KEEP=** option on the DATA statement, SAS keeps the specified variables when it writes to the output data set.

\[Chapter 11 problem 2\]
- Question (WF): For creating a new SAS dataset, can we use more than two dataset in set statement?  
- Answer (WF): Yes, by using MERGE statement.

\[Chapter 11, Problem 3\]: 
- Question (WF): Is there away to print out the FIRST. and LAST. observation within the dataset?
- Answer (WF):
```SAS
		DATA data2;
			Set data1;
			By id;
			If first.id or last.id;
		run;
		PROC PRINT data=data2;
		run;
```
\[Chapter 11 problem 3\]
- Question (WF): Can we create a new variable within a new dataset that is different from the one in set statement?  
- Answer (WF): Yes, here is an example:
```SAS
		DATA newdata;
			SET olddata;
			newvar1 = "A";
			newvar2 = 3;
		RUN;
```
- Question (WF): What is the affect on resources, when proc sort is used as compare to " BY "statement in data step?  
- Answer (WF): Sorting a data set is required when using a BY statement in a procedure, and sorting is a common and resource-intensive component of SAS. Therefore, the impact on resource would be similar.

\[Chapter 11, Problem 8\]
- Question (WF): Can an END= option have any observation in a data set and not only last?
- Answer (WF): Yes, use the END= option on a SET statement to determine the last observation of your choice in the data set.

- Question (WF): END= and POINT= are very similar, why END is to name a variable, but POINT is to get a value from the variable? 
- Answer (WF): POINT statement specifies a temporary variable whose numeric value determines which observation is read. POINT= causes the SET statement to use random (direct) access to read a SAS data set.

## Chapter 12 Questions
\[Chapter 12, Problem 1\]
- Question (WF): What situations is one-to-one matching needed since we have merge? 
- Answer (WF): In cases where you must merge certain observations, use a match-merge. For example, when merging employee information from two different data sets, it is crucial that you merge observations that relate to the same employee. Therefore, you must use a match-merge.

- Question (WF):  In 1-to-1 merging, why do same-named variables have the 2nd data set to cover while the 1st data set information does not have anything to do with the 2nd data set?
- Answer (WF): This example is a case of one-to-one matching, which requires multiple SET statements. Where same-named variables occur, values that are read from the second data set replace those read from the first data set. Also, the number of observations in the new data set is the number of observations in the smallest original data set.

- Question (WF): Can we track how many values are discarded for 1-to-1 merging with a variable?
- Answer (WF): In this case, it’s new dataset minus second dataset.

\[Chapter 12, Problem 2\]
- Question (WF): What are the pros and cons of indexing compared to sorting data for a merge?
- Answer (WF): If the data is sorted, the code that creates the index does not have to search for the correct place to store the new value, which consumes extra I/O and CPU resources. If an index is built with unsorted data, it might be larger than an index that is built with sorted data because all the pages might not be full. Sorting the data takes extra time, but generally results in a more compact index that builds faster.

\[Chapter 12, Problem 4\]
- Question (WF): If the variable types differ in the datasets to be concatenated, how can they be modified?
- Answer (WF): Using rename option to temporarily rename a variable when doing merge. For example:
```SAS
		data new;
			merge a b (rename=(pin=id));
			by id;
		run;
```
- Question (JG): What is the result of submitting the following program?

```SAS
        data work.getobs5;
            obsnum=5;
            set company.usa(keep=manager payroll) point=obsnum;
            stop;
        run;
```
- Answer (IW): The above program use *POINT* option to access 5th observation and the new output will produce the dataset work.getobs5 that contains values for manager and payroll variables for the 5th observation from company.usa dataset.  

[Chapter 12 Question 5]
- Question (SK): What if the the same name variables have different value ? Will merging work in this case?
- Answer (SK): If you have variables with the same name in more than one input data set, values of the same-named variable in the first data set in which it appears are overwritten by values of the same-named variable in subsequent data sets.

\[Chapter 12, Problem 9\]
- Question (WF): What should be done when there are more observations in the BY group but less values for variables?
- Answer (WF): Some of the observations might be duplicated records.

- Question (WF): If the dataset is large, how do I know how many observations are supposed to generate?
- Answer (WF): Here is a sample code to count observations in dataset:
```SAS
		data _null_;
			set test end=eof;
			count+1;
			if eof then call symput("nobs",count);
		run;
```

## Chapter 13 Questions
\[Chapter 13, Problem 5\]
 - Question (IW): How do you convert a numeric date, eg: 01032020 to a SAS date?
 - Answer: TBD
 
\[Chapter 13, Problem 2\]
- Question (WF): How do I convert a dollar amount to a numeric type? Do I need to strip the '$' first or is there an informat to be used?
- Answer (WF): If your string contains nondigits such as commas or dollar signs, you need to use the correct informat:
```SAS
	char_var = '$6,000,000';
	numeric_var = input(char_var,dollar10.);
```
- Question (WF): For automatic conversions that produce missing numeric values from a character value that does not conform, do the missing values appear in the log window or do they need to be identified manually?
- Answer (WF): <span id="z1375587" class="anchor"></span>SAS automatically converts character values to numeric values if a character variable is used in an arithmetic expression. If a character value contains nonnumerical information and SAS tries to convert it to a numeric value, a note is printed in the log, the result of the conversion is set to missing, and the _ERROR_ automatic variable is set to 1.

- Question (WF): If this DATA step is executed, SAS automatically converts the character value to numeric values so that calculation may occur. then what type of errors it can run into when doing the automatic conversion?
- Answer (WF): SAS prints a note in the log and assigns a missing value to the result if you try to perform an illegal operation, such as the following: dividing by zero, taking the logarithm of zero, using an expression to produce a number too large to be represented as a floating-point number (known as overflow).

\[Chapter 13, Problem 3\]
- Question (WF): what's the difference between comma6. and comma7.?
- Answer (WF): the length of the value.

\[Chapter 13, Problem 6\]
- Question (WF): How can I set the default variable length globally to something lower than 200?
- Answer (WF): SAS gives the variable a default type and length, and you cannot change the default.

\[Chapter 13, Problem 7\]



- Question (WF): Can I use negative values in SUBSTR as is the case in many other programming languages?
- Answer (WF): The SUBSTR function takes a character matrix as an argument (along with starting positions and lengths) and produces a character matrix with the same dimensions as the argument. Elements of the result matrix are substrings of the corresponding argument elements, which they are all greater than 0.

\[Chapter 13, Problem 10\]
- Question (WF): What happens if we take out the "lowcase" command?
- Answer (WF): String comparisons in SAS software are case-sensitive. For example, the uppercase letter "F" and lowercase letter "f" are treated as unique characters..
 
## Chapter 14 Questions


## Chapter 15 Questions


## Chapter 16 Questions

[Chapter 16, Problem 5]
- Question (SK): What does COMMAw.d work and how does it interpret parenthesis?
- Answer (SK): The COMMAw.d informat does more than simply read the raw data values. It removes special characters such as    commas from numeric data and stores only numeric values in a SAS data set.

## Chapter 17 Questions

[Chapter 17, Problem 2]
- Question (SK): If we are unfamiliar with the SAS dataset how will we find the formats and variable names of each dataset?
- Answer (IW): Using the Holiday dataset in SAS, use *PROC CONTENTS* statement to review variable names and format:
```SAS
    proc contents data = sashelp.holiday
	    out = data_info(keep=name type length format);
    run;
```

## Chapter 19 Questions

[Chapter 19, problem 7]
- Question (SK): What is the difference between / and #n ? Which one is more preferable / or #n in order to read data value sequentially and no sequencially?
- Answer (SK): -The / line pointer control and the #n line pointer control can be combined within a SAS program to read multiple records both sequentially and non-sequentially.The first #n line pointer control enables you to read the values for each record where as The INPUT statement uses the / line pointer control to move the input pointer forward from the first record to the second record, and from the second record to the third record.

## Chapter 20 Questions

[Chapter 20 , Problem 6]
- Question (SK): Is it possible to get the calculations like summation or average of the data values in each iteration when using @@?
- Answer: TBD
