# Markdown Refernce

## Introduction

Markdown is a lightweight markup language used to format plain text in a clean, readable, and portable way. It is widely used in GitHub repositories (READMEs, issues, documentation) and Jupyter notebooks (Markdown cells for explanations, math, and structure). This document is intended as a practical reference, not a full specification. It focuses on the Markdown features you will actually use when:
- writing project documentation
- explaining code and results
- structuring Jupyter notebooks
- creating clean, professional GitHub repositories

---

## Guide Sections
- [Headings / Sections](#headings--sections)
- [Text Formatting](#text-formatting)
- [Spacing and Line Breaks](#spacing-and-line-breaks)
- [Lists](#lists)
- [Links](#links)
- [Images](#images)
- [Code Blocks](#code-blocks)
- [Math](#math)
- [Tables](#tables)

---

## Headings/Sections
Markdown provides six levels of headings to organise content. The first typically is reserved for document title.
```markdown
# Heading (Typicaly page title)
## Subheading
### Sub-subheading
#### Sub-sub-subheading
##### Sub-sub-sub-subheading
###### Sub-sub-sub-sub-subheading
```

---

## Text Formatting

Markdown allows for all the standard text formats
```markdown
<standard typing>             # Regular text
*<italic>*                    # Italic text
**<bold>**                    # Bold text
***<bold_italic>***           # Bold + Italic
~~<strikethrough>~~           # Strikethrough text
> <block quote>               # Blockquote
>> <nested block quote>       # Nested blockquote
`<inline code>`               # Inline code                    
```
---
### Spacing and Line Breaks

---


### Lists
Lists in Markdown are used to organise items into bullet points (unordered) or numbers (ordered). Nested items can be created by indenting with spaces.
#### Unordered Lists
```markdown
- <item1>
- <item2>
    - <subitem1>
    - <subsubitem2>
        - <subsubitem1>
        - <subsubitem2>
- <item3>
```

#### Ordered Lists
```markdown
1. <item1>
2. <item2>
    1. <subitem1>
    2. <subitem2>
        1. <subsubitem1>
        2. <subsubitem2>
3. <item3>
```

---

## Links
Markdown allows you to create hyperlinks to websites, files, or sections within your document. 
```markdown
[<linkText>](<hyperlink>)       # Link to a website
[<linkText>](<filepath>)        # Link to a file    
[<linkText>](#<section>)        # Link to a section of the document
```

---

## Images 

---

## Code 

---

## Math

---

## Tables

---
