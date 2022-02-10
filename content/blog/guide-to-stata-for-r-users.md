# Stata for R users: a quick start guide

So you have an exciting international research collaboration: hurray!  Your collaborators all want to do the analysis in Stata: boo :(

While there are a lot of resources out there that teach Stata users how to work in R, the reverse is not true.  The only resources I can find on teaching R users how to use Stata is this [Stata to R cheat sheet](https://raw.githubusercontent.com/rstudio/cheatsheets/master/stata2r.pdf) which is designed for going from Stata to R, but is useful for the other direction too.  

Here are my notes on going from R to Stata, a gift from my present to my future self as I attempt to make myself Stata-literate.  If they are useful for you too, then great!  

## Some key resources

- [Getting Started with Stata](https://www.stata.com/manuals/gsw.pdf) for Windows (release 17) (abbreviated GSW below)
- [Stata to R cheat sheet](https://raw.githubusercontent.com/rstudio/cheatsheets/master/stata2r.pdf)

## Script files

Script files in Stata are called 'do-files', matching their file extension `.do`.  They are edited in the 'Do-file Editor' which you can open either with a toolbar button or Window -> Do-file Editor.  Comments in do files begin with an asterix `*` or double forward slash `//` and you can run code with the `ctrl+d` shortcut (similar to `ctrl+Enter` in R).

The basic structure of Stata syntax is

`commandname main_arguments, optional_arguments`

i.e. optional arguments that modify Stata commands are (optionally) included after a comma that follows the required arguments.  Arguments in Stata are *not* generally enclosed in brackets and, apart from the one comma above, multiple arguments are generally not separated with commas (unlike R).  

Help on Stata commands can be found using `help commandname` at the comment line or searching from the Help menu.  

## The working directory

Like R, Stata has a working directory concept.  This is the place where outputs will be saved, and is also the place Stata will look for data if importing from the command line rather than using File -> Open.  The working directory is displayed in a ribbon at the bottom of the main Stata window.  The working directory can be changed at the command line with `cd` or from the File menu.  

## Importing data

To import delimited text files such as comma-separated, tab-separated etc, use the command `import delimited` followed by the name of the file.  From GSW: "if filename contains spaces,
put double quotes around the filename, and include the path if filename is not in the current working
directory". For example:

```
import delimited my-file.csv
```

This will also import directly from a URL, for example: 

```
import delimited "https://sites.psu.edu/psucz/files/2018/09/counties90-29c6g4u.csv"
```

Excel files can be imported using `import excel`.  An example:

```
import excel "../../../Data/Boundaries/United States/ipums_puma_1990_5pct/1990_PUMAs_5pct.xls", firstrow
```

Here, the option `firstrow` tells Stata to use the first row as variable names.  Note that Stata supports relative file paths with `../` in the same way as R.  

Once imported, a dataset can be browsed using the Data Editor - a button for this is at the top of the Stata window.  The Variables Manager can be used to check the variable types and import format etc.  
  
### `no; data in memory would be lost`

So this is where Stata gets a bit frustrating for an R user.  If you try to import a second dataset after having imported another, you will get the above error message.  This is because Stata can only hold a single dataset in memory at one time.  To clear the current dataset from memory type `clear`.  Obviously this will delete any unsaved changes. 

## Renaming, dropping, reordering variables

```
keep var1 var2 ...
drop var1 var2 ...
order var1 var2 ...
rename oldname newname
```

## Create new variables 

`gen newvar = expression`

For example:

`gen fips = State * 1000 + CountyFIPScode`

This will not overwrite an existing variable - unlike R, the user will get an error message.  To overwrite an existing variable use `replace`.  

## Joining datasets

This isn't too difficult to do, but as far as I can tell so far there are some issues with doing this in Stata that are irritating to the R user who is used to the `left_join` etc functions in `dplyr`:

- only one dataset in memory at a time, so you can't look at them both 
- the variables that you are joining on must have the same name
- the external file you are merging (i.e. the one not currently in memory) must be a .dta file

The command in Stata is `merge`.  Example:

```
merge m:1 fips using counties, keepusing(ers90)
```

In this case `fips` is the variable to join on, `m:1` means many-to-one join, `counties` is the dataset brought in to merge, `ers90` is the one variable from `counties` that we want to keep when merged.  


## Erasing files 

`erase filename.ext`

I needed to do this as a consequence of having to write out a csv file as a dta file so that I could then use `merge`.  


## Descriptive statistics

`summarize` or `summ` for short, the detail option gives additional statistics.  One variable can be specified, otherwise the entire dataset is summarised (similarly to `summary()` in R).  Example:

```

```

`tabstat` and `tabulate` are useful options for categorical variables, I believe.  


## group_by() and summarise()

The equivalent to `group-by() %>% summarise()` in Stata is `collapse`.  For example

```
collapse (sum) PUMApopnincz = Areapopulation, by(ers90 State PUMA PUMApopulation)
```

This replaces the existing dataset with a collapsed dataset, grouped by the variables in `by(varlist)`.  The specification of summary values (there can be more than one) come before the comma.  Translation of the above: for records grouped by the variables in `by()`, summarise `Areapopulation` with the function `sum` and store it in a new variable `PUMApopnincz`.  If no grouping variables are specified in `by()` this summarises the entire set of observations.   
