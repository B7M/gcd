# Going from raw to tidy data

We've just spent a while discussing the principles of tidy data as well as a number of guidelines on how to correctly enter data into spreadsheets. At this point, you may think "I've got it. Make my data rectangular! I'll do it." But, the reality is that most data are untidy. If you are not the one entering the data but are instead handed the data from someone else to do a project, more often than not, those data will be untidy. Untidy data are often referred to simply as messy data.

The following common problems seen in messy data sets again come from [Hadley Wickham's paper on tidy data](http://vita.had.co.nz/papers/tidy-data.pdf). After briefly reviewing what each common problem is, we will then take a look at a few messy data sets. We'll finally touch on the concepts of tidying untidy data, but we won't actually do any practice *yet*. That's coming soon! 

### Common problems with messy data sets

1. Column headers are values but should be variable names  
2. A single column has multiple variables  
3. Variables have been entered in both rows and columns  
4. Multiple "types" of data are in the same spreadsheet  
5. A single observation is stored across multiple spreadsheets  

### Examples of untidy data

To see some of these mistakes in action, let's explore some examples!

#### Examples from [Data Organization in Spreadsheets](https://peerj.com/preprints/3183/)

In each of these examples, we see the principles of tidy data being broken. Each variable is not a unique column. There are empty cells all over the place. The data are not rectangular. Data formatted in these messy ways are likely to cause problems during analysis.

![**Examples from Data Organization in Spreadsheets**](resources/images/04_GCD_Raw_to_tidy/04_GCD_Raw_to_tidy-03.png)

For a specific example, [Miles McBain](https://milesmcbain.github.io/), a data scientist from Brisbane, Australia set out to analyze Australian survey data on Same Sex marriage. Before he could do the analysis, however, he had a lot of tidying to do. He annotated all the ways in which the data were untidy, including the use of commas in numerical data entry, blank cells, junk at the top of the spreadsheet, and merged cells. All of these would have stopped him from being able to analyze the data had he not taken the time to first tidy the data. Luckily, he wrote a [Medium piece](https://medium.com/@miles.mcbain/tidying-the-australian-same-sex-marriage-postal-survey-data-with-r-5d35cea07962) including all the steps he took to tidy the data. 

![**Miles McBain's' tidying of Australian Same Sex Marriage Postal Survey Data**](resources/images/04_GCD_Raw_to_tidy/04_GCD_Raw_to_tidy-04.png)

Inspired by Miles' work, Sharla Gelfand decided to tackle a messy data set from Toronto's open data. She similarly outlined all the ways in which the data were messy including: names and address across multiple cells in the spreadsheet, merged column headings, and lots of blank cells. She has also included the details of how she cleaned these data [in a blog post](https://sharlagelfand.netlify.com/posts/tidying-toronto-open-data/). While the details of the code may not make sense yet, it will shortly as you get more comfortable with the programming language, R.

![**Sharla Gelfand's tidying of Toronto's open data**](resources/images/04_GCD_Raw_to_tidy/04_GCD_Raw_to_tidy-05.png)

### Tidying untidy data

There are a number of actions you can take on a dataset to tidy the data depending on the problem. These include: filtering, transforming, modifying variables, aggregating the data, and sorting the order of the observations. There are functions to accomplish each of these actions in R. While we'll get to the details of the code in a few lessons, it's important at this point to be able to identify untidy data and to determine what needs to be done in order to get those data into a tidy format. Specifically, we will focus in here on a single messy data set. This is dataset D from the 'Data Organization in Spreadsheets' example of messy data provided above. We note the blank cells and that the data are not rectangular.

![**Messy data set**](resources/images/04_GCD_Raw_to_tidy/04_GCD_Raw_to_tidy-06.png)

To address this, these data can be split into two different spreadsheets, one for each type of data. Spreadsheet A included information about each sample. Spreadsheet B includes measurements for each sample over time. Note that both spreadsheets have an 'id' column so that the data can be merged if necessary during analysis. The 'note' column does have some missing data. Filling in these blank cells with 'NA' would fully tidy these data. We note that sometimes a single spreadsheet becomes two spreadsheets during the tidying process. This is OK as long as there is a consistent variable name that links the two spreadsheets!

![**Tidy version of the messy data set**](resources/images/04_GCD_Raw_to_tidy/04_GCD_Raw_to_tidy-07.png)

### Summary 

In this lesson, we looked at some of the ways that datasets can be messy and how they disagree with the principles of tidy data! We also looked at some examples of data wrangling - where people have turned messy datasets into tidy ones! While we haven't quite got there ourselves, yet, knowing these principles and what to look for are a great first step! 

### Slides

This lesson's slides can be found [here](https://docs.google.com/presentation/d/1kdSOB3RiBn-5IMJNDswI5ZNeysAN7xOsF8WXoT2PYuM/edit?usp=sharing)  
