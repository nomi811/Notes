## HTML

- *Doc Type*  -  reflects the HTML version that you are using
- *Head*  -  non-visible elements that make the page work and look right
- *Body*  -  the text that is visible
```
<"!DOCTYPE HTML">
<"html lang="en"">
   <"head">
     <"meta charset="utf-8"  -  standard always do character encoding">
     <"meta name="description" content="A page for exploring HTML documents"">
```
- *Content models*  - define the type of content expected inside an element, and control syntax rules such as element nesting.

**Two Types**
1. *Block level* - take up own line
2. *Inline level* - in the flow of other content

`&nbsp` to add a space
```
<img src="_images/lowcountry.jpg" width="300" height="300" alt="Lowcountry South Carolina">
```
example of placing an image. Do not need closing tag
`../` to go up a directory

- *Semantics* - structure of the webpage to show meaning, not just layout.

---
#### Standard Layout
**Company Information**
`<header><h1>...<h6></header>`
**Site Navigation**
`<nav></nav>`
**Main Content**
```
<section>
  <h2>...</h2>
    <article></article>
    <h3></h3>
    <article></article>
</section>
```
**Additional Information**
`<aside></aside>`
**Contact Information**
`<footer>...</footer>`

---
Think about people who use assisted technology or machines.  The heirarchy in the code must reflect the information about the content.  The code is not just for looks.  This also makes it more accessible and has better SEO.

**HTML Sectioning Elements**
`<h1>...<h6>`

`<article>` - represents a complete, or self-contained composition in a document, page, application, or site and, that is, in principle, independently distributable or reusable.  It can stand alone.

`<aside>` - a section that is related to the content, but is not essential to the document

`<nav>` - a section of a page that links to other pages or to parts within the page

`<section>` - used to delineate thematic grouping of content. Appropriate to use only if the contents would be listed explicitly in the document's outline.

`<div>` - generic container element

**HTML Semantic Elements**
`<header>, <main>, <footer>`

### Seven Models

1.  Flow
2.  Metadata
3.  Embedded
4.  Interactive
5.  Heading
6.  Phrasing
7.  Sectioning

**Flow**
Normal flow of document.  No rules how displayed.

a, abbr, address, area, article, aside, audio, b, bdi, bdo, blockquote, br, button, canvas, cite, code, data, datalist, del, dfn, div, dl, em, embed, fieldset, figure, footer, form, h1, h2, h3, h4, h5, h6, header, hr, i, iframe, img, input, ins, kbd, keygen, label, main, map, mark, math, meter, nav, nonscript, object, ol, output, p, pre, progress, q, ruby, s, samp, script, section, select, small, span, strong, style, sub, svg, table, textareas, time, u, ul, var, video, wbr
