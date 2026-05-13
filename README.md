# Bento Grid CSS

A 2-dimentional 12-column CSS grid system
bento-grid-css
Version: 1.0
Size: 4kb (not zipped)

Demo: https://simonpadbury.github.io/bento-grid-css/

## Features

* A 12 column CSS grid, with `grid-dense` and a gap variable built in
* 2 media query tiers, above which he grid columns and rows can take effect: `sm` at 640px; `md` at 960px — you can simply change these in the two `@media screen and (___) {}`
* Separate positions for control of column positions, column spans, row positions, and row spans (both up to 12)

```html
<!-- Example -->
<div class="sm:col-1 sm:colspan-6 md:colspan-3 md:row-3">...</div>
```

## How Bento Grid Works

Add the `bento` CSS class to a wrapping element (e.g. DIV), and the optional modifier `bento-dense` if you need it. This gives you _CSS grid but not defined columns_ for small devices (so that the gap still works), and a 12 column grid from `sm` 640px up.

If you add child elements (grid items), where will simply occupy 1 grid cell. They will position themselves consecutive in columns from `sm` up, with wrapping to new rows if neessary.

The simplest way to control grid items is to add `colspan-*` classes (1 to 12). The browser will automatically assign the positions, to fill the grid as best it can.

Increase complexity by using the `col-*` positioning classes. So, `sm:col-1` will position a grid item in gric cell 1 (i.e. between grid column tracks 0 and 1). And so on.

You can use `col-*` classes to change the order of your grid items in the grid cells. And, grid items will be _stacked/overlapped_ if you assign more then one to cover the same cell(s).

As described so far, Bento Grid operates similar to a “traditional” 12 column pseudo-grid system, such as in the Tailwind grid, or even the 12 column flexbox (percentile widths) pseudo-grid in older CSS frameworks such as Bootstrap and Foundation.

But now you can also coltrol row positioning and row spanning, and set up a bento-style grid. See the example HTML included.

There are two bento grid tiers, so that you can set up differently arranged bento grid layouts using `sm` for tablets in vertical orientation, and `md` for for tablets in horizontal orientation, up. (Or there are 3 tiers, if you count the “everything is in a single column” layout for phones).

## FAQ

**Q: Can this be used like a “traditional” 12-column grid system?**

A: Yes. All you need is `bento` on the wrapper, and whatever `col-*` and `colspan-*` you want on your grid items. So, you don’t need another grid system to handle a traditional layout (e.g. it could be a drop-in replacement for the Bootstrap grid in most cases, if you adjust the media queries).

**Q: How can I visualize the grid tracks while I am developing a layout?**

A: In the _browser inspector_, find the `class="bento"` wrapper, and click the small button marked [grid] that you see beside that opening HTML tag.

**Q: Why is Bento Grid not compatible with another grid system that I’m already using?**

A: This may be because both grid systems are using similar named variables, and so there’s a conflict. Try using search-and-replace on bento-grid.css to rename any or all of the following variables:

```css
--col
--colspan
--row
--rowspan
```
