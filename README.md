## Web Development Guides, Tutorials and Snippets

**Navigation**
* [Off Canvas Navigation](#off-canvas-navigation) 
* [Full Screen Navigation Overlay](#full-screen-navigation-overlay) 
* [Responsive Dropdown Navigation Bar](#responsive-dropdown-navigation-bar)

**Layout**
* [Flexbox Grid](#flexbox-grid)
* [Float Grid](#float-grid)
* [Fundamentals of Responsive Design](#fundamentals-of-responsive-design)
* [What Bootstrap Is and How To Use It](#bootstrap)


### Off Canvas Navigation
* [Tutorial](http://www.taniarascia.com/off-canvas-navigation/)
* [Demo](http://codepen.io/taniarascia/full/QjBwpB/)

### Full Screen Navigation Overlay
* [Tutorial](http://www.taniarascia.com/full-screen-navigation-overlay/)
* [Demo](http://codepen.io/taniarascia/full/yYrXRG/) 

### Responsive Dropdown Navigation Bar
* [Tutorial](http://www.taniarascia.com/responsive-dropdown-navigation-bar/)
* [Demo](http://codepen.io/taniarascia/full/dYvvYv/)

###  Flexbox Grid

* [Tutorial](http://www.taniarascia.com/easiest-flex-grid-ever/)
* [Demo](http://codepen.io/taniarascia/full/rOLEGe/)

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

* [Tutorial](http://www.taniarascia.com/you-dont-need-a-framework/)
* [Demo](http://codepen.io/taniarascia/pen/GpGdyy)

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

**Breakpoints** 
   `@media screen and (min-width: 800px) { }`
**Breakpoints** 
   `@media screen and (min-width: 800px) { }`
**Structure** – a grid system
**Navigation** – collapsible navigation


### Bootstrap

* [What Bootstrap Is and How To Use It](http://www.taniarascia.com/what-is-bootstrap-and-how-do-i-use-it/)

## Back End

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
