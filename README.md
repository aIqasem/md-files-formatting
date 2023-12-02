# Organizing .md Files (markdown files)

- [Headings](https://github.com/aIqasem/md-files-formatting#headings-)
- [Line Break](https://github.com/aIqasem/md-files-formatting#line-break-)
- [Styling](https://github.com/aIqasem/md-files-formatting#styling-)
- - [Bold](https://github.com/aIqasem/md-files-formatting#bold)
- - [Italic](https://github.com/aIqasem/md-files-formatting#italic)
- - [Bold and Italic](https://github.com/aIqasem/md-files-formatting#bold-and-italic)
- [Blockquotes](https://github.com/aIqasem/md-files-formatting#blockquotes-)
- - [Blockquotes with Multiple Paragraphs](https://github.com/aIqasem/md-files-formatting#blockquotes-with-multiple-paragraphs)
- - [Nested Blockquotes](https://github.com/aIqasem/md-files-formatting#nested-blockquotes)
- - [Blockquotes with Other Elements](https://github.com/aIqasem/md-files-formatting#blockquotes-with-other-elements)
- [Lists](https://github.com/aIqasem/md-files-formatting#lists-)
- - [Ordered Lists](https://github.com/aIqasem/md-files-formatting#ordered-lists)
- - [Unordered Lists](https://github.com/aIqasem/md-files-formatting#unordered-lists)
- - [Paragraph inside a list](https://github.com/aIqasem/md-files-formatting#paragraph-inside-a-list)
- - [Blockquote inside a list](https://github.com/aIqasem/md-files-formatting#blockquote-inside-a-list)
- [Mark a word as code](https://github.com/aIqasem/md-files-formatting#mark-a-word-as-a-code-)
- [Linking](https://github.com/aIqasem/md-files-formatting#linking-)
- [Tables](https://github.com/aIqasem/md-files-formatting/blob/main/Creating%20md%20tables%20from%20spreadsheets.md)

---

<br/>

<br/>

## Headings [..](https://github.com/aIqasem/md-files-formatting#organizing-md-files-markdown-files)

- To create a heading, add number signs (#) in front of a word or phrase. The number of number signs you use should correspond to the heading level.

```
# This is heading 1

## This is heading 2

### This is heading 3

```

_`Output`_

# This is heading 1

## This is heading 2

### This is heading 3

---

<br/>

<br/>

## Line Break [..](https://github.com/aIqasem/md-files-formatting#organizing-md-files-markdown-files)

- Best practice :

```
This is the 1st Line.<br>
And this is the 2nd one
```

_`Output`_

This is the 1st Line.<br>
And this is the 2nd one

<br/>

- This alse works .. but don't try it :

```
This is the 1st Line.<br>And this is the 2nd one
```

_`Output`_

This is the 1st Line.<br>And this is the 2nd one

---

<br/>

<br/>

## Styling [..](https://github.com/aIqasem/md-files-formatting#organizing-md-files-markdown-files)

- You can add emphasis by making text bold or italic.

<br/>

### _Bold_

- To bold text, add two asterisks or underscores before and after a word or phrase. To bold the middle of a word for emphasis, add two asterisks without spaces around the letters.

```
i am **here**.<br>
or, i**am**here. (without spaces).
```

_`Output`_

i am **here**.<br>
or, i**am**here. (without spaces).

<br/>

### _Italic_

- - To italicize text, add one asterisk or underscore before and after a word or phrase. To italicize the middle of a word for emphasis, add one asterisk without spaces around the letters.

```
i am *here*.<br>
or, i*am*here. (without spaces).
```

_`Output`_

i am _here_.<br>
or, i*am*here. (without spaces).

<br/>

### _Bold and Italic_

- To emphasize text with bold and italics at the same time, add three asterisks or underscores before and after a word or phrase. To bold and italicize the middle of a word for emphasis, add three asterisks without spaces around the letters.

```
i am ***here***.<br>
or, i<b><i>am</b></i>here. (without spaces).<br>
```

_`Output`_

i am **_here_**.<br>
or, i<b><i>am</b></i>here. (without spaces).<br>

---

<br/>

<br/>

## Blockquotes [..](https://github.com/aIqasem/md-files-formatting#organizing-md-files-markdown-files)

- To create a blockquote, add a > in front of a paragraph.

```
> This is a blockquotes
```

_`Output`_

> This is a blockquotes

<br/>

### _Blockquotes with Multiple Paragraphs_

- Blockquotes can contain multiple paragraphs. Add a > on the blank lines between the paragraphs.

```
> 1st Line of the block.
>
> 2nd one.
```

_`Output`_

> 1st Line of the block.
>
> 2nd one.

<br/>

### _Nested Blockquotes_

- Blockquotes can be nested. Add a >> in front of the paragraph you want to nest.

```
> start
>
> > this is a nested block.
>
> end
```

_`Output`_

> start
>
> > this is a nested block.
>
> end

<br/>

### _Blockquotes with Other Elements_

- looks nice? have a try

```
> try this
>
> - this is a line starting with a dot.
```

_`Output`_

> try this
>
> - this is a line starting with a dot.

---

<br/>

<br/>

## Lists [..](https://github.com/aIqasem/md-files-formatting#organizing-md-files-markdown-files)

- You can organize items into ordered and unordered lists.

<br/>

### _Ordered Lists_

To create an ordered list, add line items with numbers followed by periods. The numbers don’t have to be in numerical order, but the list should start with the number one.

```
1. 1st Line.<br>
2. 2nd Line.<br>
3. 3rd Line.<br>
```

_`Output`_

1. 1st Line.<br>
2. 2nd Line.<br>
3. 3rd Line.<br>

<br/>

### _Unordered Lists_

- To create an unordered list, add dashes (-), asterisks (\*), or plus signs (+) in front of line items. Indent one or more items to create a nested list.

```
- 1st.<br>
- 2nd.<br>
- 3rd.<br>
- - 4th (nested).<br>
```

_`Output`_

- 1st.<br>
- 2nd.<br>
- 3rd.<br>
- - 4th (nested).<br>

<br/>

- To start an unordered list with a number .. use `\` before the `.`

```
- 1st.<br>
- 2nd.<br>
- 3rd.<br>
- 4\. 4th (Starting with a number) .<br>
```

_`Output`_

- 1st.<br>
- 2nd.<br>
- 3rd.<br>
- 4\. 4th (Starting with a number) .<br>

<br/>

### _Paragraph inside a list_

- Start the paragraph with 2 spaces.

```
- 1st<br>
- 2nd <br>

  this is a test paragraph<br>

- 3rd<br>
```

_`Output`_

- 1st<br>
- 2nd <br>

  this is a test paragraph<br>

- 3rd<br>

<br/>

### _Blockquote inside a list_

- Start the line with 2 spaces.

```
- test<br>
- test<br>

  > this is s block quote.<br>

- test
```

_`Output`_

- test<br>
- test<br>

  > this is s block quote.<br>

- test

---

<br/>

<br/>

## Mark a word as a code [..](https://github.com/aIqasem/md-files-formatting#organizing-md-files-markdown-files)

`` look at this --> `test` :  ``

_`Output`_

look at this --> `test`

---

<br/>

<br/>

## Linking [..](https://github.com/aIqasem/md-files-formatting#organizing-md-files-markdown-files)

`this is a test fot this *[link](https://www.google.com/)*.<br>`

_`Output`_

this is a test fot this _[link](https://www.google.com/)_.<br>
