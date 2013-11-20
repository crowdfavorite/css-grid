### Purpose

CSSGrid is an effort to use less classes to achieve a comprehensive and flexible grid. Each element in the grid only requires one class. That means no .first or .last classes anywhere.

### Now using SASS
The `grid.css` is compiled from a SASS file, whose variables can be edited on a per-breakpoint basis. Now you can have custom grid widths, grid gutters, and column margins on each media query breakpoint. SASS will do all the heavy lifting for you, just edit `grid.scss`, compile to `grid.css` and go! There's even an option to include an even larger breakpoint in CSSGrid, if your design requires it. Simply change the `$use-lg-breakpoint` to `true` and edit the appropriate variables.

#### Variables
Make sure the variables that you choose will work with the 12-column grid. For example, a 980px-wide 12-column grid with 20px margins may have an excess of pixels, depending on which column configuration you use. This is most noticeable in Safari when using the bookmarklet and is due to subpixel rounding issues. Use a grid tool, like [gridulator](http://gridulator.com), to help you tweak your grid columns and widths to get even numbers. A 976px-wide 12-column grid with 20px margins won't have excess pixels to worry about.

### Getting Started with Rows 

Using CSSGrid is easy. It starts with a wrapper which is called .grid in this example (but you could change it to whatever you'd like). Once you've got the wrapper in place, create divs with a class of .row. Inside each row, create a set of columns for content areas.

### Column Classes

This grid is built on 12 columns and allows you to wrap your content in the desired number of columns. The grid's class names range from .c1 to .c12 for single columns, but spanning multiple columns is as simple as assigning the column span to your class. For example, .c1-4 would span the first four columns and .c5-8 would span the next three. 

CSSGrid is built on a 12 column grid. You can combine columns easily to support your different structures. Each column class is prefixed with a c designator and from there it's a simple matter of choosing the appropriate span of columns (1-n and so on) you'd wish to use.

Spanning columns is done by simply running numbers together, for example: c1-3 would be a solid div spanning three columns (or 3/12) while c4-5 would be solid div spanning two columns (2/12) wide and appearing after the first three columns.

### Nesting

Nesting is no problem. You can nest elements as deeply as you desire, and they'll just work. Here is an example of a nested content block that spans two columns.

	<div class="row">
		<div class="c1-12">
			<div class"c1-2"></div>
		</div>
	</div>


### Offsets 

This latest version of CSSGrid introduces offsets. Previously to offset a content block from the left side, you would need to place an empty div for that column. For example:

	<div class="row">
		<div class="c1"></div>
			<div class"c2-12">
    		My content here.
		  </div>
	</div>

would yield an eleven column block of content offset by one column on the left. This syntax still works, but if you'd prefer to keep your markup clear of empty divs, this new method with offsets will achieve the same results:

	<div class="row">
		<div class"c2-12 offset1">
			My content here.
		</div>
	</div>

Simply append the offset class with the number of columns to the left you're wanting to offset. n.b. Nested offsets are not supported.

### Grid Overlay

This new version of CSSGrid ships with a bookmarklet overlay to display your grid columns. The overlay is triggered via your bookmarks bar and works based on the column class names, so you can still use the bookmarklet even if you change the size of your grid structure. 

### Weight

CSSGrid means less junk in your HTML in favor of a little bit of extra CSS. Even then, CSSGrid weighs in at 8kb with comments and readable styles.

### License

CSSGrid is licensed under the [MIT License](http://opensource.org/licenses/MIT).
