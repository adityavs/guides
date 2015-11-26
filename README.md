## Web Development Guides, Tutorials and Snippets

**Navigation**
* [Full Screen Navigation Overlay](#full-screen-navigation-overlay) 
* [Off Canvas Navigation](#off-canvas-navigation) 
* [Responsive Dropdown Navigation Bar](#responsive-dropdown-navigation-bar)

**Layout**
* [Flexbox Grid](#flexbox-grid)
* [Float Grid](#float-grid)
* [Fundamentals of Responsive Design](#fundamentals-of-responsive-design)

**CSS Frameworks**
* [What Bootstrap Is and How To Use It](#bootstrap)

---

### Full Screen Navigation Overlay

A style of navigation that triggers a full screen overlay. This example utilizes flexbox.

**[Tutorial](http://www.taniarascia.com/full-screen-navigation-overlay/) &bull; [Demo](http://codepen.io/taniarascia/full/yYrXRG/)**

```css
aside {
	position: fixed;
	width: 100%;
	height: 100%;
	top: 0;
	left: 0;
	opacity: 0;
	visibility: hidden;
	z-index: 2;
}
.open {
	opacity: 1;
	visibility: visible;
}
```

```html
<aside>
  <div class="toggle-overlay">
    <a class="close"> Toggle </a>
  </div>
  <nav>
  </nav>
</aside>
```

```js
 $('.toggle-overlay').click(function() {
		$('aside').toggleClass('open');
	});
```


### Off Canvas Navigation

Slide out navigation that is hidden off canvas until triggered. Inspired by the [Lanyon/Poole theme for Jekyll](http://lanyon.getpoole.com/).

**[Tutorial](http://www.taniarascia.com/off-canvas-navigation/) &bull; [Demo](http://codepen.io/taniarascia/full/QjBwpB/)**

```css
html, body { overflow-x: hidden; }

.position {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 2;
}
@media screen and (min-width: 800px) {
  .position { position: fixed; }
}
aside {
  width: 250px;
  height: 100%;
  position: fixed;
  top: 0;
  left: -250px;
}
main {
  width: 100%;
  position: absolute;
  left: 0;
}
article {
  padding: 0 80px;
}
.show-nav aside, .show-nav .position, .show-nav main { transform: translateX(250px); }
.show-nav .position { position: fixed; }
```

```html
<aside> Navigation </aside>
<a id="nav-toggle" class="position">Toggle</a>
<main>
  <article> Main content </article>
</main>
```

```js
$('#nav-toggle').click(function () {
	this.classList.toggle("active");
	if ($('body').hasClass('show-nav')) {
		$('body').removeClass('show-nav');
	} else {
		$('body').addClass('show-nav');
	}
});
```

### Responsive Dropdown Navigation Bar

A classic top navigation bar with dropdowns. The navigation links collapse into a hamburger icon toggle on mobile collapse.

```js
$('nav ul li a:not(:only-child)').click(function (e) {
	$(this).siblings('.nav-dropdown').toggle();
	$('.nav-dropdown').not($(this).siblings()).hide();
	e.stopPropagation();
});
$('html').click(function () {
	$('.nav-dropdown').hide();
});
$('#nav-toggle').click(function () {
	$('nav ul').slideToggle();
});
```

**[Tutorial](http://www.taniarascia.com/responsive-dropdown-navigation-bar/) &bull; [Demo](http://codepen.io/taniarascia/full/dYvvYv/)**

###  Flexbox Grid

A simple, responsive grid made with flexbox. This grid is based on percentages and is infinitely expandable.

**[Tutorial](http://www.taniarascia.com/easiest-flex-grid-ever/) &bull; [Demo](http://codepen.io/taniarascia/full/rOLEGe/)**

```css
.column { flex-basis: 100% }

@media screen and (min-width: 800px) {
  .row {
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
  }
  .column { flex: 1; }
  .one-fourth { flex: 2.5; }
  .one-third { flex: 3.3; }
  .half { flex: 5; }
}
```

```html
<div class="row">
  <div class="column"> 50% </div>
  <div class="column"> 50% </div>
</div>
```

### Float Grid

A simple, responsive grid made with CSS floats and a clearfix hack. This grid is based on percentages rather than the traditional 12-column grid. You can add as many classes as you want columns.

**[Tutorial](http://www.taniarascia.com/you-dont-need-a-framework/) &bull; [Demo](http://codepen.io/taniarascia/pen/GpGdyy)**

```css
.row::before, .row::after {
  display: table;
  content: " ";
  clear: both;
}
.one, .one-third, .two-thirds, .one-fourth, .half { width: 100%; }

@media only screen and (min-width: 800px) {
  .one { width: 100%; }
  .half { width: calc(100% / 2); }
  .one-third { width: calc(100% / 3); }
  .one-fourth { width: calc(100% / 4); }
  .two-thirds { width: calc(100% / 3 * 2); }
  .column { float: left }
}
```
```html
<div class="row">
  <div class="half column"> 50% </div>
  <div class="half column"> 50% </div>
</div>
```

### Fundamentals of Responsive Design
* [Understanding the Fundamentals of Responsive Design](http://www.taniarascia.com/you-dont-need-a-framework/)

1. **Foundation** - `<meta name="viewport" content="width=device-width, initial-scale=1">`
1. **Breakpoints** - `@media screen and (min-width: 800px) { }`
1. **Structure** - a grid system
1. **Navigation** - collapsible navigation

### Bootstrap

* [What Bootstrap Is and How To Use It](http://www.taniarascia.com/what-is-bootstrap-and-how-do-i-use-it/)



### Dev Environments

* [Setting Up a Local Server Environment with MAMP](http://www.taniarascia.com/local-environment/)
* [Setting Up Virtual Hosts](http://www.taniarascia.com/setting-up-virtual-hosts/)

### Content Management System (CMS)

* [Developing a WordPress Theme from Scratch](http://www.taniarascia.com/developing-a-wordpress-theme-from-scratch/)
* [Migrating a WordPress Site to a Live Server](http://www.taniarascia.com/migrating-a-wordpress-site-to-a-live-server/)

### Git

* [Getting Started with Git](http://www.taniarascia.com/getting-started-with-git/)

### Task Runners

* [Getting Started with Grunt and Sass](http://www.taniarascia.com/getting-started-with-grunt-and-sass/)

### APIs

* [Google Maps APIs for Multiple Locations](http://www.taniarascia.com/google-maps-apis-for-multiple-locations/)
