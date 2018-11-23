---
id: semantic-elements
title: Semantic Elements
---

[HTML5 Semantic Elements](https://www.w3schools.com/html/html5_semantic_elements.asp)

## main tag

* The `main` tag specifies the main content of a document.
* There must not be more than one `main` element in a document.
* The content inside the `main`  element should be unique to the document. It should not contain any content that is repeated across documents such as sidebars, navigation links, copyright information, site logos, and search forms.

参考资料：

* [HTML main Tag](https://www.w3schools.com/tags/tag_main.asp)

## article tag

* `article` is a sectioning element, and is used to wrap independent, self-contained content.
* Potential sources for the `article` element
    * Forum post
    * Blog post
    * News story
    * Comment
* 在 HTML5 中，`article` 元素可以看做一种特殊种类的 `section` 元素，它比 `section` 元素更强调独立性。

参考资料：

* [Wrap Content in the article Element](https://learn.freecodecamp.org/responsive-web-design/applied-accessibility/wrap-content-in-the-article-element/)
* [HTML article Tag](https://www.w3schools.com/tags/tag_article.asp)
* 《HTML 5 与 CSS 3 权威指南》（第3版）第三章 3.1.1 article 小节

## section tag

* It's used to wrap introductory information or navigation links for its parent tag, and works well around content that's repeated at the top on multiple pages.
* section 元素中需包含标题。
* section 元素的作用是对页面上的内容进行分块，或者说对文章进行分段，不要将它与表示“有着自己的完整的、独立的内容”的 article 元素混淆。
* 不要将 section 元素用作设置样式的页面容器，因为那是 div 元素的工作。

参考资料：

* [Wrap Content in the article Element](https://learn.freecodecamp.org/responsive-web-design/applied-accessibility/wrap-content-in-the-article-element/)
* 《HTML 5 与 CSS 3 权威指南》（第3版）第三章 3.1.2 section 小节

## article 和 section 的区别

* `article` and `section` can be used within each other, as needed. For example, if a book is the `article`, then each chapter is a `section`.
* `section` 元素强调分段或分块，而  `article` 强调独立性，具体来说，如果一块内容相对来说比较独、完整的时候，应该使用 `article` 元素，但是如果想将一块内容分成几段的时候，应该使用 `section` 元素进行分段。

## header tag

- `header` 元素是一种具有引导和导航作用的结构元素，通常用来放置整个页面或页面内的一个内容区块的标题，也可以包含数据表格、搜索表单或相关的 LOGO 图片。
- 一个网页内并不限制只能有一个 `header` 元素，可以拥有多个，可以为每个内容区块加一个 `header` 元素。
- 一个 `header` 元素通常包含至少一个 heading 元素。

参考资料：

- 《HTML 5 与 CSS 3 权威指南》（第3版）第三章 3.2.1 header 小节

## nav tag

- `nav` tag is meant to wrap around the main navigation links in your page.
- If there are repeated site links at the bottom of the page, it isn't necessary to markup those with a nav tag as well. Using a footer is sufficient.

参考资料：

- [Make Screen Reader Navigation Easier with the nav Landmark](https://learn.freecodecamp.org/responsive-web-design/applied-accessibility/make-screen-reader-navigation-easier-with-the-nav-landmark)

## footer tag

- It's primarily used to contain copyright information or links to related documents that usually sit at the bottom of a page.

参考资料：

- [Make Screen Reader Navigation Easier with the footer Landmark](https://learn.freecodecamp.org/responsive-web-design/applied-accessibility/make-screen-reader-navigation-easier-with-the-footer-landmark)

## figure and figcaption tag

- Used together, these items wrap a visual representation (like an image, diagram, or chart) along with its caption.

example:

```html
<figure>
  <img src="roundhouseDestruction.jpeg" alt="Photo of Camper Cat executing a roundhouse kick">
  <br>
  <figcaption>
    Master Camper Cat demonstrates proper form of a roundhouse kick.
  </figcaption>
</figure>
```

参考资料：

- [Improve Chart Accessibility with the figure Element](https://learn.freecodecamp.org/responsive-web-design/applied-accessibility/improve-chart-accessibility-with-the-figure-element/)

## audio tag

- The HTML5 `<audio>` element specifies a standard way to embed audio in a web page.

```html
<audio controls>
  <source src="horse.ogg" type="audio/ogg">
  <source src="horse.mp3" type="audio/mpeg">
Your browser does not support the audio element.
</audio>
```

参考资料：

- [HTML5 Audio](https://www.w3schools.com/html/html5_audio.asp)

## time tag

- The `<time>` tag defines a human-readable date/time.
- This element can also be used to encode dates and times in a machine-readable way so that user agents can offer to add birthday reminders or scheduled events to the user's calendar, and search engines can produce smarter search results.

```html
<p>We open at <time>10:00</time> every morning.</p>

<p>I have a date on <time datetime="2008-02-14 20:00">Valentines day</time>.</p>
```

## form element

- Improve form field accessibility with the label element
- Wrap radio buttons in a fieldset element for better accessibility
- Add an accessible date picker

```html
<form>
  <fieldset>
    <legend>Choose one of these three items:</legend>

    <input id="one" type="radio" name="items" value="one">
    <label for="one">Choice One</label><br>

    <input id="two" type="radio" name="items" value="two">
    <label for="two">Choice Two</label><br>

    <input id="three" type="radio" name="items" value="three">
    <label for="three">Choice Three</label>

    <label for="input1">Enter a date:</label>
    <input type="date" id="input1" name="input1">
  </fieldset>
</form>
```
