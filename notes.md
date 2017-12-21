# Accessibility Workshop Notes

a11y - because there 11 letters between the A and the Y.

## Basics

Using HTML elements for their intended purpose is always easier from an
accessibility perspective than trying to coerce something. For example, using an
unordered list makes your life easier than trying to style a bunch of spans into
a list.

Try your pages out - dump the mouse and try navigate only with
keyboard....notice things like how long list of checkboxes are very frustrating
to tab through. Use voiceover to see how your page does with screenreaders.

### Voiceover cheatsheet

Watch the [intro](https://www.youtube.com/watch?v=5R-6WvAihms)

| Shortcut | Description |
| -------- | -------- |
| cmd-f5 | toggle on/off |
| ctrl-u | rotor |
| ctrl | toggle start/stop reading |
| ctrl-right-arrow | next thing |

### Accessibility inspector

In chrome, go to
[chrome://flags/#enable-devtools-experiments](chrome://flags/#enable-devtools-experiments
).

Enable dev tools experiments.

In the inspector, open Settings -> Experiments and check "Accessibility
Inspection".

Restart chrome.

You should now have an Accessibility tab in the inspector.

## Keyboard interaction

HTML elements that are interactive (buttons, form elements etc) by default allow
keyboard interaction. Keep this in mind if you co-erce a non-interactive element
to look and behave like an interactive element.

There are subtle differences between interactions. A button will respond to both
a `spacebar` click and a `enter` button click. An `href` will only respond to a
`enter` button click. So if you style a link to look like a button, it won't
work the same way by default.

### Tab order

Tab order follows the order in the DOM.

If you use fancy things like flexbox or grid layouts or even just css to move
items into a different order, you break tab order.

Using `tabindex="n"` is usually a bad idea.

## Accessible Rich Internet Applications (aria)

Use native HTML elements whenever possible.

Use aria roles when creating structures not apparent from the elements
themselves. For example, creating a tabbed interface with `divs` and `spans`.

### Give every interactive element an accessible name.

Links are named for the text between the `a` tags.

Use the `alt` tag on images.

Use `for` on labels in forms.

Fieldsets and legends inside forms group related content.

If you have something like a button with an icon as the only clue to its intent
(e.g. a search button which has a magnifying glass), use an
`aria-label="search"` to help screenreaders make sense of the element.

### Application role gotcha

Doing this:

```
<body role="application">...</body>
```

stops the screenreader commands from working.

## Hiding things

Use `hidden` to hide elements - e.g. `<nav hidden>...</nav>`.

Using `style="display:none"` will hide from everyone unless css is disabled.

## Links

[Accessibility community](https://www.gov.uk/service-manual/communities/accessibility-community)

[Service
manual](https://www.gov.uk/service-manual/helping-people-to-use-your-service)
