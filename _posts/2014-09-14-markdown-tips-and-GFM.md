---
layout: post
title: Markdown tips and GFM
description: Markdown tips and github flavored markdown
category: programthinking
---

Markdown tips and GFM
======

markdown: easy-to-write, easy-to-read, plain text format

Basic:
------

1. Parahraphs: one or more blank lines
2. Headings:
```
# head1 #
## head2 ##
...
###### head6 ######
```
or "===", "---"
3. Blockquotes:
<pre><code> 
> blockquotes
</code></pre>
4. styling text:
   ```
   *bold*, _bold_
   **italic**, __italic__
   **_bold&italic_**
   ```
5. seperated lines: 3 or more * and -

Lists
------

  1. unordered lists: *, -, +
  2. ordered list: 1., 2., ...
  3. nested lists
    ```
    1. line1
    2. line2
      * subline1
      * subline1
    3. line3
    ```
    
Code formatting:
------

1. inline lines: ``` `code` ```
2. multiple lins: ` ```code block``` `

Links
------

1. 
  ```[link_text](link_url)```
2. 
  ```
  [link_text](link_id)
  
  link_id: link_url "optional_link_title"
  ```
3. 
  ```
  [link_text][]
  
  links: link_url "optional_link_title"

  ```
4. images:
  ```
  ![Alt text](path/to/img.jpg)
  ![Alt text](path/to/img "optional_title")
  ```
5. auto links: 
  ```
  <link>
  ```
  
Special Character: 
------

1. `<` and `&`, when they are not in code block, it will transferred to `&lt;` and `&amp;`
2. need `\` to display:
  ```
  \
  `
  *
  _
  {}
  []
  ()
  #
  +
  -
  .
  !
  ```

GFM(Github Flavored Markdown)
======

1. it_is_not_italic
2. URL autolinking as `http://github.com` will transfer to http://github.com
3. `~~strikethrough~~` --> ~~strikethrough~~
4. Fenced code blocks
5. Syntax highlighting
  <pre><code>
  ```ruby
  require 'redcarpet'
  markdown = Redcarpet.new("Hello World!")
  puts markdown.to_html
  ```
  </code></pre>

6. Tables:
```
| Left-Aligned  | Center Aligned  | Right Aligned |
| :------------ |:---------------:| -----:|
| col 3 is      | some wordy text | $1600 |
| col 2 is      | centered        |   $12 |
| zebra stripes | are neat        |    $1 |
```
will become

| Left-Aligned  | Center Aligned  | Right Aligned |
| :------------ |:---------------:| -----:|
| col 3 is      | some wordy text | $1600 |
| col 2 is      | centered        |   $12 |
| zebra stripes | are neat        |    $1 |
