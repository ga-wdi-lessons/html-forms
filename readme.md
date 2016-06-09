# HTML Forms

## Learning Objectives

- Querystrings
- GET vs POST
- Elements and attributes
- Targeting checked elements with CSS

## Framing

This class is our introduction to sending data through the web.

## Querystrings

If you use Reddit's search bar to search for "cats" you're taken to a URL like this:

```
https://www.reddit.com/search?sort=relevance&t=month&q=cats
```

- What do you think the `q` stands for?
- What seems to be the purpose of the text after the `?`?
- Try changing what comes after `q=`. What happens?
- Google something. What does the URL look like?

Finally, go to the [Project 1 Gallery repo](https://github.com/ga-dc/project1-gallery) and click the "Submit your project here." link.

- What do you notice about the URL?
- What happens if you add `?body=banana` to the end?

This is called a **querystring**. It's a way of passing data into a webpage.

<details>
<summary>What seem to be the "rules" of querystrings?</summary>

They are `key=value` pairs, separated by `&`, following a `?`, and are the last part of the URL.
</details>

### Accessing querystrings with Javascript

Add a querystring to this (or any) page. Then, open up the browser console and type in `console.dir(window.location)`. Look at the details of the result.

- What do you see?
- In which property is the querystring? How do you know?
- Why might this be useful? How might you use it?

### URL encoding

Go back to Google and search for a complete sentence with punctuation in it. For example:

> I like bananas, coconuts, & grapes.

- What happens to the punctuation?

Search for `!-_/?#&`.

- Which punctuation marks stay the same in the URL? Which don't? Why is this necessary?

Open up the browser console and type:

```
encodeURIComponent("!-_/?#&");
```

- How is this similar to the Google URL?

Try it again with a complete sentence:

```
encodeURIComponent("I like bananas, coconuts, & grapes.");
```

- How is this different from the Google URL?

<!-- The spaces are percent-encoded -->

Try playing with `decodeURIComponent()`.

## Creating and Submitting Forms

[HTML Forms Practice](https://github.com/ga-wdi-exercises/html-forms-practice)

## GET vs POST
