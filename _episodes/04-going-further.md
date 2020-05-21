---
title: Going further
teaching: 0
exercises: 0
questions:
- What else can I do with Regex?
objectives:
- Orientation to other concepts
keypoints:
- There is a lot to regular expressions!  It's OK to use a cheat sheet.
---

# Exercises

## Flags
> - `/i` renders an expression case-insensitive (equivalent to `[A-Za-z]`).

> ## Escaping metacharacters
> Since regular expressions define some ASCII characters as "metacharacters" that have more than their literal meaning, it is also important to be able to "escape" these metacharacters to use them for their normal, literal meaning. For example, the period `.` means "match any character", but if you want to match a period then you will need to use a `\` in front of it to signal to the regular expression processor that you want to use the period as a plain old period and not a metacharacter. That notation is called "escaping" the special character. The concept of "escaping" special characters is shared across a variety of computational settings, including markdown and Hypertext Markup Language (HTML).
- `\` is used to escape the following character when that character is a special character. So, for example, a regular expression that found `.com` would be `\.com` because `.` is a special character that matches any character.


> ## Using regular expressions when working with files and directories
>
> One of the reasons we stress the value of consistent and predictable directory and filenaming conventions is that working in this way enables you to use the computer to select files based on the characteristics of their file names. For example, if you have a bunch of files where the first four digits are the year and you only want to do something with files from '2017', then you can. Or if you have 'journal' somewhere in a filename when you have data about journals, you can use the computer to select just those files. Equally, using plain text formats means that you can go further and select files or elements of files based on characteristics of the data *within* those files. See Workshop Overview: [File Naming & Formatting](https://librarycarpentry.org/lc-overview/06-file-naming-formatting/index.html) for further background.
>
{: .callout}

This logic is useful when you have lots of files in a directory, when those files have logical file names, and when you want to isolate a selection of files. It can be used for looking at cells in spreadsheets for certain values, or for extracting some data from a column of a spreadsheet to make new columns. There are many other contexts in which regex is useful when using a computer to search through a document, spreadsheet, or file structure. Some real-world use cases for regex are included on an [ACRL Tech Connect blog](https://acrl.ala.org/techconnect/post/fear-no-longer-regular-expressions/)

# Extracting a substring in Google Sheets using regex

> ## Extracting a substring in Google Sheets using regex
> 1. Export and unzip the [2017 Public Library Survey](https://github.com/LibraryCarpentry/lc-data-intro/blob/gh-pages/files/PLS_FY17.zip) (originally from the IMLS data site) as a CSV file.
> 2. Upload the CSV file to Google Sheets and open as a Google Sheet if it doesn't do this by default.
> 3. Look in the `ADDRESS` column and notice that the values contain the latitude and longitude in parenthesis after the library address.
> 4. Construct a regular expression to match and extract the latitude and longitude into a new column named 'latlong'. HINT: Look up the function `REGEXEXTRACT` in Google Sheets. That function expects the first argument to be a string (a cell in `ADDRESS` column) and a quoted regular expression in the second.
>
>> ## Solution
> > This is one way to solve this challenge. You might have found others. Inside the cell you can use the below to extract the Latitude and Longitude into a single cell. You can then copy the formula down to the end of the column.
>>~~~
> > =REGEXEXTRACT(G2,"\d+\.\d+, -?\d+\.\d+")
> >~~~
> >{: .source}
> > Here we are using `\d+` for a one or more digit match followed by a period `\.`. Note we had to escape the period using `\`. After the period we look for one or more digits  `\d+` again followed by a literal comma `,`. We then have a literal space match followed by an optional dash `-` (there are few `0.0` Latitude/Longitudes that are probably errors, but we'd want to retain so we can deal with them). We then repeat our `\d+\.\d+` we used for the Latitude match.
> {: .solution}
{: .challenge}
