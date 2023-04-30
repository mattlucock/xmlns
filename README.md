# xmlns

[![npm version](https://img.shields.io/npm/v/xmlns?style=flat-square)](https://npm.im/xmlns)
[![License](https://img.shields.io/github/license/mattlucock/xmlns?style=flat-square)](https://github.com/mattlucock/xmlns/blob/main/LICENSE.md)

This package is a very simple repository of XML namespaces that you can import into your code wherever you need them.

```js
export const MATHML_NS = 'http://www.w3.org/1998/Math/MathML'
export const SVG_NS = 'http://www.w3.org/2000/svg'
export const TTML_NS = 'http://www.w3.org/ns/ttml'
export const XHTML_NS = 'http://www.w3.org/1999/xhtml'
```

This is obviously not an exhaustive list of XML namespaces, but this package can very easily be extended with pull requests to specify additional namespaces if appropriate.

## Why this package

XML namespaces are special strings that you have to reproduce in your code *exactly* (including with correct casing). The default way to find the value of a namespace, every time you need one, is to literally look it up and then copy-paste it from a reference into your code, which is obviously not ideal. Even less ideal is storing the value of namespaces in your code. For example, when calling `document.createElementNS`, you have to quote the namespace every time, so it's probably a good idea to store it in a variable. But where should you define this variable? In general you would define it as some kind of shared/common/global variable so that you can import it in multiple files, but this is very awkward. The truth is that there's no logical place for the namespace to live in your code because the value is not actually related to your code.

This package gives you XML namespaces wherever you need them without having to worry about where they are defined or what their values actually are. This package is very brief, but if this package feels silly, it's because XML namespaces are silly. There are a few packages on NPM for creating SVG elements in the DOM, but these packages basically just wrap `document.createElementNS`, and the only real value they provide is that they include the value of the SVG namespace. This package is a superior solution to the same problem.
