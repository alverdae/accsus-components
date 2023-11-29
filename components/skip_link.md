# Skip link

## What is it?
A skip link is the first focusable link on a web page with with a keyboard user can go directly to the main content of the web page. It is a way to skip blocks of repeated content. The skip link is usually hidden, but gets shown when it receives keyboard focus.

## Why do we need it?
Keyboard users use the Tab key to navigate through interactive elements on a web page. It is cumbersome if they need to tab through repeated content - such as a main menu - on every page. 

## How to implement?
First: you need to locate the start of the unique content of the page. In this example this is the main element with `id="site-content"`. This is standard for WordPress websites, but you can edit this: 
```<main id="site-content">```

Second: you need to add an anchor link at the start of the `<body>` tag, because this needs to be the first focusable element (except for eventual dialogs). This is an anchor link to the element with `id="site-content"`. We also add a class to this link, so that it can be styled: 
```<a class="skip-link" href="#site-content">Skip to the content</a>```

Third: to make sure that the skip link is only visible when it receives focus, you need to style it accordingly. In the first CSS code we place it off screen: 

```
.skip-link {
    position: absolute;
    left: -10000px;
    top: auto;
    width: 1px;
    height: 1px;
    overflow: hidden;
}
```

In the next CSS code we make the skip link visible on focus:

```
.skip-link:focus {
    position: static;
    width: auto;
    height: auto;
}
```

## References
- [Understanding WCAG 2.2 success criterion 2.4.1 "Bypass blocks" (Level A)](https://www.w3.org/WAI/WCAG22/Understanding/bypass-blocks.html)
- [W3Schools - Accessibility Skip Links](https://www.w3schools.com/accessibility/accessibility_skip_links.php)

[Back to Components](/accsus-components/components/)