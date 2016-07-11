# Fabricator Width Awareness Component

While this component is designed with the [BuzzingPixel Fabricator Build Process](https://github.com/tjdraper/buzzing-pixel-fabricator) in mind, it can be used anywhere (in theory).

## `FAB.widthAwareness.add();`

Adds an element to width awareness watching.

### `add()` argument 1

The first argument can be a jQuery selector string, a DOM object, or a jQuery object.

### `add()` additional arguments

The second argument can be an array of sizes to add to the element, or all additional arguments after the first can be integer sizes to add for watching on the element.

## `FAB.widthAwareness.remove()`

Remove elements from being watched by width awareness.

Takes one argument: a jQuery selector string, a DOM object, or a jQuery object.

## `FAB.widthAwareness.watchSelector();`

Adds anything that matches the selector to width awareness watching, and watches the DOM for new selectors that match and adds them when they are added to the DOM.

Additional arguments work just like the `add` function where the second can be an array, or all additional arguments can be integers.

## `$('.myClass').trigger('widthAwarenessCheck')`

Using the jquery trigger method, you can trigger a `widthAwarenessCheck` on your element to force it to update rather than waiting for a window resize event.

## Styling

If you do not pass custom sizes, a default set is used (400, 500, 600, and on up through 1800). Regardless, as each width of the element is reached, the width is added to the data-widths attribute on the element. So you can use the space separator selector to look for it like so:

```
.myClass {
	background: red;
}
.myClass[data-widths~="400"] {
	background: blue;
}
.myClass[data-widths~="800"] {
	background: yellow;
}
```

## Classes and Data Elements

Any element with the class .js-width-aware or the data attribute data-width-aware="true" already on the DOM or inserted onto the DOM will be made width aware and will receive the default set of width aware sizes.