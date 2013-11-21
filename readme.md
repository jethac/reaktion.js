Reaktion JS
========

Reaktion JS is a lightweight, flexible jQuery plugin for generating responsive, nested navigation menus. It allows developers to get up and running extremely quickly and is completely customizable. By default it uses [Font Awesome](http://fortawesome.github.io/Font-Awesome/) instead of images and contains a LESS file with variables for easy customization. For more information including documentation and integration examples please visit the [Reaktion JS website](http://reaktionjs.com)

Demo
------

You can view the different demo's on the [Reaktion JS website](http://reaktionjs.com/demos)

Usage
------

Add the css file to the `<head>` of your document (Font Awesome is optional but recommended, please see the [customization](#customization) section for details):

```html
<link rel="stylesheet" href="/css/reaktion.css" />
<link rel="stylesheet" href="//netdna.bootstrapcdn.com/font-awesome/4.0.3/css/font-awesome.min.css" >
```

Add jQuery and Reaktion JS at the bottom of your document before the end `</body>` tag:

```html
<script src="//ajax.googleapis.com/ajax/libs/jquery/1.10.2/jquery.min.js"></script>
<script src="reaktion.min.js"></script>
```

Create the HTML markup for the navigation menu:

```html
<div class="nav">
	<ul>
		<li><a href="#">Menu Item</a></li>
		<li><a href="#">Menu Item</a>
			<ul>
				<li><a href="#">Sub Menu Item</a></li>
				<li><a href="#">Sub Menu Item</a></li>
				<li><a href="#">Sub Menu Item</a></li>
			</ul>
		</li>
		<li><a href="#">Menu Item</a></li>
		...
	</ul>
</div>
```

And last but not least call the plugin:

```html
$(function(){ 
	$('.nav').reaktion(); 
});
```




Customization
------

There are several ways to customize Reaktion JS for you needs, the two most common are via plugin options and CSS:

### Options

| Option | Default | Type | Description |
| -------| --------| -----| ------------|
| breakPoint | `768` | int | Refers to the viewport width and determines when the navigation switches to the "mobile" version.|
| navIcon | `<i class="fa fa-bars"></i>` | string | The HTML (text, icon, image, etc.) for the mobile icon (the mobile icon is what the user clicks to reveal the mobile menu. |
| arrows | `true` | bool | Whether or not to show the sub menu arrows. To include the arrows on the "mobile" version only you can use CSS to hide them (ie: `.nav ul li span.arrow { display:none; }`) |
| arrowIcon | `<i class="fa fa-chevron-down"></i>` | string | The HTML (text, icon, image, etc.) for the sub menu arrows.|
| arrowsToggleOnly | `true` | bool | If `true`, the arrows are the only element that will toggle the sub menus, if `false` the parent link of the sub menu will also toggle sub menus. Does not apply if arrows are disabled.
| animate | `true` | bool | Whether or not to animate the mobile menu on reveal |
| effect | `slide` | string | The effect used to animate the mobile menu, can be either `slide` or `fade` |
| speed | `300` | int | The speed at which to animate the mobile menu |
| animateSubNav | `true` | bool | Whether or not to animate when opening the sub menus |
| subNavEffect | `slide` | string | The effect used to animate the sub menus, can be either `slide` or `fade` |
| subNavSpeed | `300` | int | The speed at which to animate the sub menus |

Below is an example using these options in the plugin call:

```html
$(function(){ 
	$('.nav').reaktion({
		breakPoint: 768,
	    navIcon: '<i class="fa fa-bars"></i>',
	    arrows: true,
	    arrowIcon: '<i class="fa fa-chevron-down"></i>',
	    arrowsToggleOnly: true,
	    animate: true,
	    effect: 'slide',
	    speed: 300,
	    animateSubNav: true,
	    subNavEffect: 'slide',
	    subNavSpeed: 300
	});
});
```

### CSS

Reaktion JS comes with a CSS file (`css/reaktion.css`) that contains the basic styling for the menu. This file is compiled from the LESS file (`less/reaktion.less`) that is also included. You are free to use either one but the LESS file contains a few varibales that make it easier to customize quickly.  For more details on how to style Reaktion JS for your needs please see the [documentation](http://reaktionjs.com/docs).

### API

Reaktion JS contains API methods for opening and closing the menu after initialzation:

```html
// Dom ready
$(function(){ 
	// Initialize
	$('.nav').reaktion();
	// open the mobile menu
	$('.nav').reaktion('open'); 
	// close the mobile menu
	$('.nav').reaktion('close'); 
	// toggle the mobile menu
	$('.nav').reaktion('toggle');
});	 
```

## License

Reaktion JS is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT)





