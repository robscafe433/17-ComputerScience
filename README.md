# Regex Tutorial: Understanding Common Regular Expressions

## Introduction
This tutorial provides an in-depth explanation of several commonly used regular expressions (regex). Regular expressions are sequences of characters that define search patterns, which can be used for validating input, searching text, and more. In this document, we will cover the following regex patterns:

- Matching a Hex Value
- Matching an Email
- Matching a URL
- Matching an HTML Tag

## Table of Contents
- [1. Matching a Hex Value](#1-matching-a-hex-value)
- [2. Matching an Email](#2-matching-an-email)
- [3. Matching a URL](#3-matching-a-url)
- [4. Matching an HTML Tag](#4-matching-an-html-tag)

## 1. Matching a Hex Value
The regex for matching a hex value is:

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/

### Explanation
- `^` asserts the start of the string.
- `#?` allows for an optional hash (`#`) at the beginning.
- `([a-f0-9]{6}|[a-f0-9]{3})` matches either six or three hexadecimal characters (0-9, a-f).
- `$` asserts the end of the string.

### Examples
- Valid: `#abc123`, `abc`, `#fff`
- Invalid: `#12345g`, `#12345`, `abc1234`

## 2. Matching an Email
The regex for matching an email address is:

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

### Explanation
- `^` asserts the start of the string.
- `([a-z0-9_\.-]+)` matches the local part of the email, which can contain letters, digits, underscores, dots, and hyphens.
- `@` is a literal character separating the local part from the domain.
- `([\da-z\.-]+)` matches the domain name, which can include digits, letters, dots, and hyphens.
- `\.([a-z\.]{2,6})` matches the top-level domain (TLD) which must be between 2 to 6 characters long.
- `$` asserts the end of the string.

### Examples
- Valid: `user@example.com`, `john.doe123@domain.org`
- Invalid: `@domain.com`, `user@.com`

## 3. Matching a URL
The regex for matching a URL is:

/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w\.-]*)*\/?$/

### Explanation
- `^(https?:\/\/)?` optionally matches the protocol (http or https).
- `([\da-z\.-]+)` matches the domain name.
- `\.([a-z\.]{2,6})` matches the TLD.
- `([\/\w \.-]*)*` matches the path, which can include slashes, words, dots, and hyphens.
- `\/?` optionally allows for a trailing slash.
- `$` asserts the end of the string.

### Examples
- Valid: `https://www.example.com`, `http://example.org/path/to/resource`
- Invalid: `htp://example.com`, `www.example.com`

## 4. Matching an HTML Tag
The regex for matching an HTML tag is:

/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/


### Explanation
- `^<([a-z]+)` matches the opening angle bracket followed by the tag name.
- `([^<]+)*` matches any attributes that may be present.
- `(?:>(.*)<\/\1>|\s+\/>)` matches either a closing tag or a self-closing tag.
- `$` asserts the end of the string.

### Examples
- Valid: `<div>Content</div>`, `<img src="image.jpg" />`
- Invalid: `<div><p></div>`, `<tag>`

## Conclusion
This tutorial provides a comprehensive overview of some common regex patterns. Understanding these regex patterns will help you validate and manipulate strings effectively in your applications.
