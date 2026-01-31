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
<regular_text>                # Regular text
*<italic>*                    # Italic text
**<bold>**                    # Bold text
***<bold_italic>***           # Bold + Italic
~~<strikethrough>~~           # Strikethrough text
> <block_quote>               # Blockquote
>> <nested_block_quote>       # Nested blockquote            
```
---
## Spacing and Line Breaks

---

## Lines and Breaks

---


## Lists
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

## Tables

Markdown allows you to create simple tables using pipes `|` and hyphens `-`. They can also be aligned

### Basic Tables
```markdown
| Header 1 | Header 2 | Header 3 |
|----------|----------|----------|
| Row 1A   | Row 1B   | Row 1C   |
| Row 2A   | Row 2B   | Row 2C   |

### Aligned Tables
| Left Align | Center Align | Right Align |
|:-----------|:------------:|------------:|
| Item 1     | Item 2       | Item 3      |
| Item 4     | Item 5       | Item 6      |

---

## Links
Markdown allows you to create hyperlinks to websites, files, or sections within your document. 
```markdown
[<linkText>](<https://example.com>)     # Link to a website
[<linkText>](</Folder/File>)            # Link to a file    
[<linkText>](#<section>)                # Link to a section of the document
```

---

## Images 
Markdown allows you to add images in from the interenet or saved in the repository
```markdown
![<Alt_Text](<https://example.com/image.png>)   # Inserts image from the internet   
![<Alt_Text](</Images/Image.png>)               # Inserts image from repository using relative path
```

---

## Code 
Markdown allows you to add code either in line or in a block

### Inline Code
```markdown
`<inline_code>`     # Highlights code within a sentence
```

### Code Blocks
Use triple backticks for multi-line code blocks, optionally specifying the language for syntax highlighting.
```markdown
```<language>
<code>
# ```               # Remove # to close code block
```

---

## Math
Markdown allows you to add math through LaTeX typesetting. You can include inline math or display math.
```markdown
$<LaTex_Code>$          # Inserts inline math
$$<LaTex_code>$$        # Inserts display math, centered on a new line
```