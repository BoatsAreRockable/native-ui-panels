# native-ui-panels
**native-ui-panels** is a Node.js module that can be used to create panels that look similar to the native ones in Windows. Designed specifically for usage in [NW.js](/nwjs/nw.js) applications.

![Screenshot](http://i.imgur.com/c0D6NBZ.png?1)
## Install
```shell
npm install native-ui-panels
```

## Example
```js
var panels = require("native-ui-panels");

// Create some content to put in the panel
var div = document.createElement("div");
var content = document.createTextNode("content");
div.appendChild(content);

panels("example", {
  title: "Hello world",
  content: div,
});
```

## Usage
```js
panels(id, {options});
```
### id *required*
Type: `String`
Default: `null`

This sets the value of the `id` attribute of the created panel.

### options
#### options.title
Type: `String`
Default: `""`

The text to be displayed in the title bar of the panel.

#### options.content
Type: `Node` or `String`
Default: `null`

The contents of the panel.

If `options.content` is a `Node`, it can either be an element already in the DOM which will be removed and reinserted in the panel or an element created using `document.createElement`.

If `options.content` is a `String`, the string will be inserted in the panel as HTML.

#### options.width
Type: `String`
Default: `auto`

The width of the panel. Accepts any valid CSS length property.

#### options.height
Type: `String`
Default: `auto`

The height of the panel. Accepts any valid CSS length property.

#### options.color
Type: `String`
Default: `#000000`

The color of the panel's surrounding frame. Setting this to `auto` will get the theme color from the Windows registry.

#### options.posX
Type: `String`
Default: `5em`

The location of the panel from the left edge of the window. Accepts any valid CSS length property.

#### options.posY
Type: `String`
Default: `5em`

The location of the panel from the top edge of the window. Accepts any valid CSS length property.

#### options.blocking
Type: `Boolean`
Default: `false`

Toggle if the panel prevents other elements from being selected when it is visible.

#### options.canClose
Type: `Boolean`
Default: `true`

This toggles if a close button should be displayed on the title bar of the panel.

#### options.canDrag
Type: `Boolean`
Default: `true`

This toggles whether the panel can be moved or not.


#### options.visible
Type: `Boolean`
Default: `false`

This toggles whether to display the panel.

#### options.scrollPageIfOverflow
Type: `Boolean`
Default: `false`

This toggles the behaviour when a panel is dragged to the edge of the window.
* `true`: If the panel is dragged to edge of the window, scrollbars will be displayed on the window to allow the entire panel to be viewed.
* `false`: If a section of the panel extends beyond edge of the window it will be hidden.

## License
MIT
