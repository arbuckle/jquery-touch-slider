A Mobile Image Gallery That Won't Embarrass You And Bring Shame To Your Family
==============================================================================

(eventually)

So this is a work in progress, prompted by the complete lack of any sane or reasonable touch galleries on the web.

Not that any sane or reasonable person would pick this up and use it in its present state.

The jQuery plugin model was selected in order to allow for multiple instances of the gallery to be painlessly used on a single page.

Initially, it was planned to allow the plugin to be instantiated against a DIV that contained a bunch of <img> tags, and the plugin would automatically parse the image paths out of the DIV, load the slider framework, and lazy-load all the images in the background.  Unfortunately, the presence of the <img> tags on page load results in the mobile browser immediately requesting all those images, causing a very slow page load.  Instead, image paths are now passed into the plugin as follows:

	$('MyTouchSlider').touchFlipper({
		'images': [	'0.jpg',
				'1.jpg',
				'2.jpg']
	});

This may change.  The plugin is in development.

Objectives
----------
* Duplicate the look and feel of the native Android image gallery.
* Center images in the viewport while preserving their aspect ratio. |SUPPORTED|
* Leverage GPU-accelerated CSS translations to animate gallery. |SUPPORTED|
* Touch events allow user to swipe left and right to view images. |SUPPORTED|
* Tap once to expose Next/Prev controls and menu options.  Tap again to remove them. |SUPPORTED|
* Easily customizable menu options.
* Full-viewport mode - the gallery takes up the entire viewport, with enough height to suppress the address bar.
* Integrated mode - the gallery can be integrated as an inline element of the page. |SUPPORTED|
* Displays a working page immediately when requested.  Images and data are filled in as the connection allows.
* Work cross-browser:  Android browser, HTC Sense browser, Mobile Safari, Mobile Firefox, Mobile Opera, IE9.
* Handle funky edge cases such as 1-2 images per gallery.
* Handle irresponsible developers who wish to include 100s or 1000s of images in a single gallery.