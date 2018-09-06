---
layout: post
title: Some markdown tips and Github Flavored Markdown
description: Markdown tips and github flavored markdown
category: 技术
tags: Markdown
---

Refer [Issue#4](https://github.com/qiwihui/qiwihui.github.io/issues/4) to see more details about write markdown code in markdown.
markdown: easy-to-write, easy-to-read, plain text format.
<!--more-->

Basic:
------

1. Parahraphs: one or more blank lines
2. Headings:
    <pre><code> &#35; head1 &#35;
    &#35;&#35; head2 &#35;&#35;
    ...
    &#35;&#35;&#35;&#35;&#35;&#35; head6 &#35;&#35;&#35;&#35;&#35;&#35;</code></pre>
or
    <pre><code> Head1
    &#61;&#61;&#61;&#61;&#61;&#61;
    Head2
    &#45;&#45;&#45;&#45;&#45;&#45;</code></pre>

3. Blockquotes:
    <pre><code>> blockquotes</code></pre>

4. styling text:
   <pre><code>&#42;bold&#42;, &#95;bold&#95;
   &#42;&#42;italic&#42;&#42;, &#95;&#95;italic&#95;&#95;
   &#42;&#42;&#95;bold&italic&#95;&#42;&#42;</code></pre>

5. seperated lines: 
    <pre><code> &#42; &#42; &#42;
    &#42;&#42;&#42;
    &#42;&#42;&#42;&#42;&#42;&#42;
    &#45; &#45; &#45;
    &#45;&#45;&#45;&#45;&#45;&#45;</code></pre>

Lists
------

1. unordered lists: 
    <pre><code>*, -, +</code></pre>

2. ordered list: 
    <pre><code> &#185;.  Bird
    &#178;.  McHale
    &#179;.  Parish</code></pre>

3. nested lists
    <pre><code> &#185;. line1
    &#178;. line2
      &#42; subline1
      &#42; subline1
    &#179;. line3</code></pre>

Code formatting:
------

1. inline lines:
    <pre><code>&#96;code&#96;</code></pre>

2. multiple lins:
    <pre><code> &#96;&#96;&#96;
    require 'redcarpet'
    markdown = Redcarpet.new("Hello World!")
    puts markdown.to_html
    &#96;&#96;&#96;</code></pre>

Links
------

1. basic
  <pre><code>&#91;link_text&#93;&#40;link_url&#41;</code></pre>

2. seperated
  <pre><code>&#91;link_text&#93;&#40;link_id&#41;
  link_id: link_url "optional_link_title"</code></pre>

3. with optional text
  <pre><code>&#91;link_text&#93;&#40;&#41;
  links: link_url "optional_link_title"</code></pre>

4. images:
  <pre><code>&#33;&#91;Alt text&#93;&#40;path/to/img.jpg&#41;
  &#33;&#91;Alt text&#93;&#40;path/to/img "optional_title"&#41;</code></pre>

5. auto links:
  <pre><code> &#60;link&#62;</code></pre>

Special Character:
------

1. `<` and `&`, when they are not in code block, it will transferred to `&lt;` and `&amp;`

2. need `\` to display:
  <pre><code>\
  `
  *
  _
  {}
  []
  ()
  &#35;
  +
  &#45;
  .
  ! </code></pre>

GFM(Github Flavored Markdown)
======

1. `it_is_not_italic`
2. URL autolinking as <code>http://github.com</code> will transfer to [http://github.com](http://github.com)
3. `~~strikethrough~~` --> ~~strikethrough~~
4. Fenced code blocks
5. Syntax highlighting
  <pre><code>&#96;&#96;&#96;ruby
  require 'redcarpet'
  markdown = Redcarpet.new("Hello World!")
  puts markdown.to_html
  &#96;&#96;&#96; </code></pre>

6. Tables:
<pre><code>| Left-Aligned  | Center Aligned  | Right Aligned |
| :------------ |:---------------:| -----:|
| col 3 is      | some wordy text | $1600 |
| col 2 is      | centered        |   $12 |
| zebra stripes | are neat        |    $1 |
</code></pre>
will become

| Left-Aligned  | Center Aligned  | Right Aligned |
| :------------ |:---------------:| -----:|
| col 3 is      | some wordy text | $1600 |
| col 2 is      | centered        |   $12 |
| zebra stripes | are neat        |    $1 |
