---
title: Matching & Substitution
teaching: 20
exercises: 20
questions:
- How do you find and replace strings with regular expressions?
objectives:
- Test knowledge of use of regular expressions
keypoints:
- Regular expressions answers
---


# Substitutions


# Capturing groups

## Exercise: Adding a time zone to an ISO timestamp

Start with: https://regex101.com/r/Lgan8n/2

How would you add this time zone to indicate the hour offset from UTC time?

> ## Greedy vs Lazy matches
>
> Using the `?` character you can control whether you get the largest continuous match possible or the smallest match possible.  In this case we are testing `.*,` (Greedy) which matches from the beginning of the line up to the last comma.  `.*?,` (Lazy) will match just to the first comma.
> Example using: https://regex101.com/r/39aKyj/2
{: .callout}

## Live coding with a text editor: Modifying award numbers

Example string: A list of NSF award numbers</br>
`1928753, 1927277, 1928771, 1928817, 1928609, 1928761`

1. How would you transform a comma-delimited list on one line into one award number per line?

2. How would we add the prefix "OCE-" to each of these award numbers to indicate they are from the Division of Ocean Sciences?

3. OK great! Now how can we turn these into a list of links to the NSF award page at nsf.gov?
</br>
Example: </br>OCE-1259043, https://www.nsf.gov/awardsearch/showAward?AWD_ID=1259043


> # Regex interoperability
>
> How do you match strings in different languages, text editors and the command line?
>
> Languages have various packages and modules for regular expressions.  Regex101.com includes a code generator that will show how your regular expression could be used on your test string with the results printed.
>
> Try going to https://regex101.com/r/2mr2t3/6 and clicking "Code Genererator" in the left panel then "Python" to get to example code: https://regex101.com/r/2mr2t3/6/codegen?language=python
>
> Now go back to https://regex101.com/r/2mr2t3/6 and in the left panel change from "Python" to "PCRE."  Can you see the difference?
> How would you modify this expression for PCRE? Hint: Hover over the characters highlighted in red to see a tip.
{: .callout}

# Exercises

### Choose your own Adventure!

Take a few minutes and come up with your own regular expression example using regex101.com.  When you are done, paste the link to your completed example in the collaborative document.

It can be anything! It could even use some of your own data. If you need inspiration, you can modify any of the examples in this section or use the Code of Conduct as a test string (https://regex101.com/r/e1qcEh/1).
