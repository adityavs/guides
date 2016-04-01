# Web Development Guides, Tutorials and Snippets

*Update 2/16/16 - Added Gulp workflow tutorial*

Guides, tutorials, demos and snippets for front end and back end web development.

## Design

* [Full Screen Navigation Overlay](#full-screen-navigation-overlay) 
* [Off Canvas Navigation](#off-canvas-navigation) 
* [Responsive Dropdown Navigation Bar](#responsive-dropdown-navigation-bar)
* [Flexbox Grid](#flexbox-grid)
* [Float Grid](#float-grid)
* [Fundamentals of Responsive Design](#fundamentals-of-responsive-design)
* [What Bootstrap Is and How To Use It](#bootstrap)

## Development

* [Local Server Environment (MAMP)](#local-server-environment---mamp)
* [Virtual Hosts](#virtual-hosts)
* [Developing a WordPress Theme from Scratch](#developing-a-wordpress-theme-from-scratch)
* [Developing a WordPress Theme from Scratch (Part 2)](#developing-a-wordpress-theme-from-scratch-part-2)
* [Migrating WordPress](#migrating-wordpress)
* [Getting Started with Git](#getting-started-with-git)
* [Using Grunt and Sass](#using-grunt-and-sass)
* [Making a Static Website with Jekyll](#using-jekyll)
* [Installing, Using and Understanding Sass](#learn-sass-now)
* [Guide to Installing and Using Gulp](#guide-to-installing-and-using-gulp)

## Systems

* [Setting Up a Virtual Server (EC2 Instance)](#setting-up-ec2-with-aws)
* [Enable HTTPS with an SSL/TLS Certificate on Apache](#enable-https-with-an-ssltls-certificate)

## JavaScript Day by Day

* [JavaScript Day One: Comments, Variables, Data Types, and Hello, World!](https://www.taniarascia.com/javascript-day-one/)

**[More](#more)**


---

### Full Screen Navigation Overlay

A style of navigation that triggers a full screen overlay. This example utilizes flexbox.

**[Tutorial](https://www.taniarascia.com/full-screen-navigation-overlay/) &bull; [Demo](http://codepen.io/taniarascia/full/yYrXRG/)**

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

**[Tutorial](https://www.taniarascia.com/off-canvas-navigation/) &bull; [Demo](http://codepen.io/taniarascia/full/QjBwpB/)**

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

**[Tutorial](https://www.taniarascia.com/responsive-dropdown-navigation-bar/) &bull; [Demo](http://codepen.io/taniarascia/full/dYvvYv/)**

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

###  Flexbox Grid

A simple, responsive grid made with flexbox. This grid is based on percentages and is infinitely expandable.

**[Tutorial](https://www.taniarascia.com/easiest-flex-grid-ever/) &bull; [Demo](http://codepen.io/taniarascia/full/rOLEGe/)**

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

**[Tutorial](https://www.taniarascia.com/you-dont-need-a-framework/) &bull; [Demo](http://codepen.io/taniarascia/pen/GpGdyy)**
d
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

Before integrating third party frameworks into your websites, learn how to build your own simple framework and understand responsive breakpoints, grids, and navigation styles.

**[Understanding the Fundamentals of Responsive Design](https://www.taniarascia.com/you-dont-need-a-framework/)**

1. **Foundation** - `<meta name="viewport" content="width=device-width, initial-scale=1">`
1. **Breakpoints** - `@media screen and (min-width: 800px) { }`
1. **Structure** - a grid system
1. **Navigation** - collapsible navigation

### Bootstrap

Bootstrap is one of the most popular CSS frameworks. Learn what a framework is, how to get started with Bootstrap, and how to use the documentation to build a responsive frame upon which you can add custom styles.

**[What Bootstrap Is and How To Use It](https://www.taniarascia.com/what-is-bootstrap-and-how-do-i-use-it/)**

* What is Bootstrap?
* Why is a framework important?
* Building a basic Bootstrap template
* Applying custom styles

### Local Server Environment - MAMP

Setting up a local environment is necessary In order to begin working in the back end with languages such as PHP and MySQL. Learn how to set up a LAMP/MAMP/WAMP stack.

**[Setting Up a Local Server Environment with MAMP](https://www.taniarascia.com/local-environment/)**

* Linux/Mac/Windows
* Apache
* MySQL
* PHP

### Virtual Hosts

If you want to set up more than one websites on a local server, you can use virtual hosts to work on as many sites as you want.

**[Setting Up Virtual Hosts](https://www.taniarascia.com/setting-up-virtual-hosts/)**

* Editing the Apache configuration file - `httpd.conf`
* Editing the hosts files - `hosts`
* Setting the correct ports


### Developing a WordPress Theme from Scratch

You know HTML, but your potential clients don't. If you intend to make a website and pass it on to a user so that they might edit it by themselves in the future, a **content management system** (CMS) will be necessary. WordPress is the most popular CMS, and it's built on PHP.

This guide will show you how to take your HTML site and turn it into a WordPress theme. It assumes no prior knowledge of PHP or WordPress.

**[Developing a WordPress Theme from Scratch](https://www.taniarascia.com/developing-a-wordpress-theme-from-scratch/)**

### Developing a WordPress Theme from Scratch Part 2

Expanding on the original article, you will learn how to do the following:

* Create individual post pages – single.php
* Add pagination
* Include comments
* Learn how to use functions.php
* Properly enqueue stylesheets and scripts
* Create global custom fields
* Create custom post types

**[Developing a WordPress Theme from Scratch Part 2](https://www.taniarascia.com/wordpress-from-scratch-part-two/)**

### Migrating WordPress

After creating a WordPress theme in a local environment, there are a few necessary steps to take to ensure that the site doesn't break when migrating to a live server.

**[Migrating a WordPress Site to a Live Server](https://www.taniarascia.com/migrating-a-wordpress-site-to-a-live-server/)**

### Getting Started with Git

Links to Git repositories are everywhere. Learn how to use the command line to create a local project, upload it to a Git repository host (such as GitHub), and upload it onto a live server, bypassing FTP.

This guide assumes no prior knowledge with or familiarity of Git, GitHub, version control software, or using command lines.

**[Getting Started with Git](https://www.taniarascia.com/getting-started-with-git/)**

### Using Grunt and Sass

Understanding how to use Node.js, Node Package Manager (npm), Grunt, Sass, and command line can be daunting. This guide assumes no prior knowledge of using the command line, installing Node.js, using npm, Grunt or Sass, and details every step along the way to ensure that Grunt it up and running. 

By the end of this article you will be able to set up Grunt and use it to compile SCSS into CSS which is minified and autoprefixed, as well as minifying and linting JavaScript code.

**[Getting Started with Grunt and Sass](https://www.taniarascia.com/getting-started-with-grunt-and-sass/)**

### Using Jekyll

Use Jekyll, the static site generator, to create a dynamically generated static website, and push it to GitHub pages.

**[Making a Static Website with Jekyll](https://www.taniarascia.com/make-a-static-website-with-jekyll/)**

### Learn Sass Now

Sass is a CSS preproccessor that can make writing CSS faster and more efficient. You might have heard of Sass, but not know how to set it up or integrate it with your projects. We’ll go over all of that in this tutorial for Mac and Windows.

**[Installing, Using, and Understanding Sass](https://www.taniarascia.com/learn-sass-now/)**

### Guide to Installing and Using Gulp

Gulp is a task runner which makes it easy to run redundant tasks without thinking about them. In the case of this article, we'll learn all the necessary prerequisites to installing Gulp, and create a task which compiles SCSS to CSS, minifies, and adds vendor prefixes.

**[Installing and Using Gulp for Front End Web Development](https://www.taniarascia.com/getting-started-with-gulp/)

### Setting Up EC2 with AWS

Amazon Web Services, or AWS, is a popular platform for deploying cloud based apps. Learn how to set up a virtual server in the cloud with AWS EC2 instances.

**[Getting Started with AWS - Setting Up a Virtual Server](https://www.taniarascia.com/getting-started-with-aws-setting-up-a-virtual-server/)**

### Enable HTTPS with an SSL/TLS Certificate

Learn how to encrypt your server by enabling HTTPS on your website with a TLS/SSL certificate. Also includes information on how to properly hook up HTTPS with WordPress.

[Obtain a TLS/SSL Certificate and Enable HTTPS Encryption](https://www.taniarascia.com/https-ssl-tls-certificate-how-to/)

### More

* [Common Development Terms and Abbreviations](https://www.taniarascia.com/development-terms-abbreviations/)
* [Google Maps APIs for Multiple Locations](https://www.taniarascia.com/google-maps-apis-for-multiple-locations/)

**In Progress**
* [Start Making Websites.com](http://startmakingwebsites.com/) - A Beginner's Guide to Web Development
* [HTML Cheat Sheet](http://startmakingwebsites.com/html) - List of all commonly used HTML5 valid tags
