---
id: attributes-relative-to-keyboard
title: Attributes Relative to the Keyboard
---

## accesskey

HTML offers the accesskey attribute to specify a shortcut key to activate or bring focus to an element. This can make navigation more efficient for keyboard-only users.

HTML5 allows this attribute to be used on any element, but it's particularly useful when it's used with interactive ones. This includes links, buttons, and form controls.

```html
<button accesskey="b">Important Button</button>
```

参考资料：

- [Make Links Navigatable with HTML Access Keys](https://learn.freecodecamp.org/responsive-web-design/applied-accessibility/make-links-navigatable-with-html-access-keys/)
- [HTML accesskey Attribute](https://www.w3schools.com/tags/att_accesskey.asp)

## tabindex

- When tabindex is on a tag, it indicates that element can be focused on.
- Certain elements, such as links and form controls, automatically receive keyboard focus when a user tabs through a page.
- his same functionality can be given to other elements, such as `div`, `span`, and `p`, by placing a `tabindex="0"` attribute on them.

```html
<div tabindex="0">I need keyboard focus!</div>

<div tabindex="1">I get keyboard focus, and I get it first!</div>

<div tabindex="2">I get keyboard focus, and I get it second!</div>
```

参考资料：

- [Use tabindex to Add Keyboard Focus to an Element](https://learn.freecodecamp.org/responsive-web-design/applied-accessibility/use-tabindex-to-add-keyboard-focus-to-an-element/)
- [Use tabindex to Specify the Order of Keyboard Focus for Several Elements](https://learn.freecodecamp.org/responsive-web-design/applied-accessibility/use-tabindex-to-specify-the-order-of-keyboard-focus-for-several-elements/)
