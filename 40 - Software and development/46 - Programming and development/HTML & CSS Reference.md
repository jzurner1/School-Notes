# Terms
- **Block-level elements**: A type of display value. These always start on a new line and contain a margin before and after the element. They always take up the entire width of the page. Common examples include `<p>` and `<div>`.
- **Inline elements**: A type of display value. These do not start on a new line and only take up as much width as is necessary. Common examples include `<span>` and `<img>`.
- **Inline block elements**: These are combinations of block-level and inline elements. They take up the width of their content, but they can have set sizes.
- **Content**: The content of a container, where text and images appear.
- **Padding**: Clears an area around the content between the content and the container's border; this is transparent.
- **Border**: A border that goes around the padding and content, can be set to have a custom width, style, and color.
- **Margin**: Clears an area outside the border; this is transparent.
- **Pseudo-class**: A pseudo-class is a special state of an element, such as when an element is moused over or clicked on. It is used to style the element differently in those cases. It is written in CSS as `selector:pseudo-class {}`, such as `a:visited {}`.

# Elements
- `a`: Used to add links, often in conjunction with the `href` attribute.
- `body`: The main body portion of a webpage.
- `fieldset`: Used to group related items in a form.
- `form`: Used to create an HTML form.
- `h1`: Headings of various sizes, `h1` being the largest and `h6` the smallest.
- `hr`: Create a horizontal divider line.
- `html`: Defines the root of the HTML document.
- `img`: Used to add images, often in conjunction with the `src` and `alt` attributes.
- `input`: Create an input section, usually within an HTML form.
- `label`: Used to extend the selectable box of HTML forms.


# Properties
- `background`: Used with the `linear-gradient` function to create color gradients.
- `background-color`: The background color of an element. Like other forms of color, this can be set to hex, rgb, or color names.
- `color`: Change the text color of an element.
- `font-family`: The font used within the element. To add a fallback font (in the event that the main font isn't found), add it after a comma.
- `font-style`: Change the style of the font, such as italic.
- `height`: Change the height of an object.
- `margin`: Adjust the margins of an item. This changes all four sides of a margin.
	- Using `margin-left` and `margin-right` and setting them to `auto` will center a container within its parent.
	- You can also use negative margins to move the opposite direction.
- `max-width`: Set the maximum width of an element, used when an element has adjustable width (such as when set with `width`). Usually measured in terms of pixels.
- `opacity`: Adjust how transparent the item is.
- `padding`: Adjust the padding of an item.
- `text-align`: Adjust the horizontal alignment of text within its parent container.
- `width`: Change the width of an object.