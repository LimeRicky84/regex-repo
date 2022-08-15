# Matching an Email

Introductory paragraph (replace this with your text)

## Summary

In this regex tutorial, I'm going to break down all the components of a regular expression made to find an email address within the text
of a document to explain what they do and why they work.

The whole regex is as follows: <code>/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/</code>.
((Briefly summarize the regex you will be describing and what you will explain.)) 

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

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

### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)