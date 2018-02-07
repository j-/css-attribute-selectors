CSS Attribute Selectors
=======================

> Match on the presence or value of a given attribute


Selectors
---------


### `[attr]`

Represents an element with an attribute name of `attr`.

```css
a[title] {
  color: red;
}
```

```html
<!-- No match -->
<a href="#">Link</a>

<!-- Match -->
<a href="#" title="Hello world">Link</a>
```


### `[attr=value]`

Represents an element with an attribute name of `attr` whose value is exactly
`value`.

```css
a[href=one] {
  color: red;
}
```

```html
<!-- No match -->
<a href="poney">Link</a>

<!-- Match -->
<a href="one">Link</a>
```


### `[attr~=value]`

Represents an element with an attribute name of `attr` whose value is a
whitespace-separated list of words, one of which is exactly `value`.

```css
input[placeholder~=search] {
  color: red;
}
```

```html
<!-- No match -->
<input placeholder="First name">

<!-- Match -->
<input placeholder="Enter search term">
```


### `[attr|=value]`

Represents an element with an attribute name of `attr` whose value can be
exactly `value` or can begin with `value` immediately followed by a hyphen, `-`
(U+002D). It is often used for language subcode matches.

```css
body[lang|=en] {
  color: red;
}
```

```html
<!-- No match -->
<body lang="zh">

<!-- Match -->
<body lang="en es">
<body lang="en-US">
```


### `[attr^=value]`

Represents an element with an attribute name of `attr` whose value is prefixed
(preceded) by `value`.

```css
a[href^="/"] {
  color: red;
}
```

```html
<!-- No match -->
<a href="../foobar">Relative</a>

<!-- Match -->
<a href="/foobar">Absolute</a>
```


### `[attr$=value]`

Represents an element with an attribute name of `attr` whose value is suffixed
(followed) by `value`.

```css
a[href$=".pdf"] {
  color: red;
}
```

```html
<!-- No match -->
<a href="report.html">HTML file</a>

<!-- Match -->
<a href="repord.pdf">PDF download</a>
```


### `[attr*=value]`

Represents an element with an attribute name of `attr` whose value contains at
least one occurrence of `value` within the string.

```css
div[class*=bar] {
  color: red;
}
```

```html
<!-- No match -->
<div class="foo baz"></div>

<!-- Match -->
<div class="foobar baz"></div>
```


### `[attr operator value i]`

Adding an `i` (or `I`) before the closing bracket causes the value to be
compared case-insensitively (for characters within the ASCII range).

```css
input[value*=invalid i] {
  color: red;
}
```

```html
<!-- No match -->
<input value="Valid value">

<!-- Match -->
<input value="Invalid value">
```


Links
-----

* [Attribute selectors on MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors)
