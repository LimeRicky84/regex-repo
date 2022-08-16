# Matching an Email

The following gist is an explaination of a regex one might use to find an email in a text document.

## Summary

In this regex tutorial, I'm going to break down all the components of a regular expression made to find an email address within the text
of a document to explain what they do and why they work.

The whole regex is as follows: <code>/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/</code>.
((Briefly summarize the regex you will be describing and what you will explain.)) 

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

A regex, being a literal, must begin and end with the slash character (<code>/</code>). However, JavaScript provides a second way, called a RegExp 
constructor, using quotation marks instead of slashes. RegExp constructors are outside of the scope of this document, those
interested in learning more can start here: 

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp

### Anchors

Anchor characters, like <code>^</code> and <code>$</code> are meant to signify the text preceding the symbol (<code>$</code>),
or the text following it (<code>^</code>).  The email regex we're examining in this document uses both, as you can see in the following
snippets:

 <code>/^([a-z0-9_\.-]+)</code>
 and:
 <code>([a-z\.]{2,6})$/</code>
 
 The first snippet refers to the group of symbols that follow (<code>[a-z0-9_\.-]</code>), the second refers to the characters preceding
 (<code>[a-z\.]</code>). But why not these <code>{2,6}</code> characters? Because they are quantifiers, which we will discuss in the following section.  
 
 To see the explaination of bracket expressions (<code>[]</code>) look [here](#bracket-expressions).
 
 To see the explaination of parenthetic expressions (<code>()</code>) look [here](#grouping-and-capturing).

### Quantifiers

The quantifiers in our regex look like this <code>{2,6}</code>, but what do they mean?

(<code>{}</code>) curly brackets set limits for a match. In this case, numbers are added to signify the maximum and minimum amount
of times that the pattern should match as follows: <code>{ (min), (max) }</code>

So, the whole snippet: <code>([a-z\.]{2,6})</code> reads characters from a to z and a literal dot (<code>.</code>) should show up at least two times, but no more than six. Common examples might be: <code>.com</code> or <code>.gov</code>

### Character Classes

There are a few character classes in this regex, so we will look at them all.  If we take a look at the entire regex:

<code>/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/</code>

The first character class we see is <code>a-z</code>, representing any lowercase alphabetical character between a and z.

The next character class is <code>0-9</code>, representing any integer between 1 and 9.

The character class <code>\d</code> also represents integers.

### Flags

A flag is not present in this regex, but some common ones are:

<code>g</code> (global) does not return after the first match, and restarting following searches from the end of the last match.

<code>m</code> (multi-line) using <code>^</code> and <code>$</code> to start and end the line instead of searching an entire string.

<code>i</code> (insensitive) to remove case sensitivity.

### Grouping and Capturing

Using parentheses (<code>()</code>) within a regex can be useful when extracting info from strings or data using a specific language.
Or, you may want to check multiple parts of a string to determine that different sections fulfill different requirements.  The sections
can be broken up with grouping constructs.  Each of these sections are called subexpressions.

### Bracket Expressions

When someting is inside a set of (<code>[]</code>) square brackets, those patterns, called bracket expressions, or positive character
groups, represent a range of characters that we want to match.

in the email example, <code>[a-z0-9_\.-]</code> this section represents two character classes, <code>a-z</code> representing letters,
and <code>0-9</code> for integers.  The other symbols <code>_\.-</code> allow for the inclusion of underscores, dots and hyphens along
with the earlier mentioned characters.

In this section <code>[\da-z\.-]</code> the regex is searching for essentially the same thing, minus the underscore, and in this section
<code>a-z\.</code> the search includes letters and dots (<code>.</code>).

### Greedy and Lazy Match

The quantifiers (<code>* + {}</code>) are greedy operators.  In the case of this regex, the (<code>+</code>) quantifier matches
any of the listed characters one or more times.

## Author

I'm Eric Madsen, I'm currently enrolled in a coding bootcamp at the U of U.  Check out my GitHub at this link here: https://github.com/LimeRicky84