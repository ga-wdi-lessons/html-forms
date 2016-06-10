# HTML Forms

## Learning Objectives

- Encode and decode a querystring
- Explain the differences between GET and POST
- Identify common HTML elements and attributes used to send data

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

[HTML Forms Practice](http://ga-wdi-exercises.github.io/html-forms-practice/index.html)

### Questions

<details>
<summary>What are the 4 different values for the `type` attribute you've seen?</summary>
`radio`, `checkbox`, `text`, `submit`
</details>

<details>
<summary>On what 2 elements can the `checked` attribute be used?</summary>
`input type="radio"`, `input type="checkbox"`
</details>

<details>
<summary>On what 1 element can the `selected` attribute be used?</summary>
`<option>`
</details>

<details>
<summary>What 2 elements are necessary to make a dropdown menu?</summary>
`<select>` and `<option>`
</details>

<details>
<summary>What other attribute does the `for` attribute correspond to?</summary>
The value of `for` must be the ID of an element.
</details>

<details>
<summary>What's the difference between `name` and `value`?</summary>
When you submit a form, the data is sent as key/value pairs. `name` is the key. For instance, if you submit a form with `<input name="color" value="red" />` the data will contain `color=red`.
</details>

<details>
<summary>For what elements is there a `[]` in the name? Why is it necessary?</summary>
The elements that allow multiple answers for one field have `[]`. This is array notation, because the elements have an array of values.
</details>

## GET vs POST

The `method` attribute on the `<form>` element can have one of two values: `get` or `post`.

### What's the difference?

Clone down the [HTML Forms Practice repo](https://github.com/ga-wdi-exercises/html-forms-practice), or just copy its HTML source into an `index.html` on your computer.

On the `<form>` element, change the `method` to `post` and submit the form.

- What's different from when the `method` was `get`?
- After submitting the form, try refreshing the page. Does anything pop up?

Leaving the `method` as `post`, change the `action` to `http://putsomethinghere.com/post.php`.

> This is a blank site I own but am currently not doing anything with.

Submit the form again.

- What do you see?

Leaving the `action`, change the `method` back to `get` and submit the form.,

- What do you see?
- What's different from when the `method` was `get`?
- Refresh the page. Does anything pop up?

Leaving the `method`, change the `action` to `http://putsomethinghere.com/get.php` and submit the form.

- What do you see?
- Refresh the page. Does anything pop up?

In your browser go to http://putsomethinghere.com/get.php . Type in a querystring (and don't forget the leading `?`).

- What happens?

### So what *is* the difference?

`GET` sends data as a querystring in your URL. `POST` hides the data when it's sent.

- Why might this distinction be useful?
- In what situations would having data in the querystring be useful? (Hint: Think back to the first part of this class.) When would it be *bad*?
- In what situations would having hidden data be useful?
- What do the **English words** "get" and "post" mean **in English**?

### HTTP methods

Your web browser can communicate with a server in several ways, like you can communicate with another person by whispering, shouting, sending a letter, or sending a text.

The whole system of browsers communicating with servers is called "HTTP" (HyperText Transfer Protocol). GET and POST are two ways of communicating within that system.

There are several other HTTP methods, which we'll see later. `<form>` elements can only either GET or POST.

## Styling Forms

Adding CSS to your forms can be extremely important for a good UI.

- Using your form, find out what each of the following CSS selectors does, and why they might be useful?

```
:checked
:focus
[type="something"]
input + label
input:checked + label
```

- Which elements **can't** really be styled with CSS?

### You Do: [Cat Fancy](https://github.com/ga-wdi-exercises/cat_fancy)
