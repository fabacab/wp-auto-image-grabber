=== WP-Auto Image Grabber ===
Author: Meitar Moscovitz
Plugin URL: http://maymay.net/blog/projects/wp-auto-image-grabber/
Donate link: https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=TJLPJYXHSRBEE&lc=US&item_name=Donation%20to%20support%20WP%2dAuto%20Image%20Grabber%20plugin&item_number=wp%2dauto%2dimage%2dgrabber&currency_code=USD&bn=PP%2dDonationsBF%3abtn_donateCC_LG%2egif%3aNonHosted
Tags: images, automation
Requires at least: 2.6
Tested up to: 3.0.1
Stable tag: 0.2

Inserts an image from a page you link to at the start of your blog post. A simple algorithm tries to get a "main content" image, not an ad.

== Description ==

Inserts an image from a page you link to at the start of your blog post. A simple algorithm tries to get a "main content" image (rather than an advertisement), automatically providing your post with relevant, attributed artwork. This is especially useful for bloggers who syndicate posts to sites like Facebook or Digg, which use the first image in a post as a thumbnail for their post.

This plugin **requires PHP 5**; sites running on PHP 4 will produce fatal errors.

By default, the plugin will follow the first link in your blog post and grab what it thinks is an appropriate main content image from there. If your posts follow a particular structure or pattern, you can tell the plugin to follow a certain link (such as a link with a particular `class`) by setting the `Pointer element for destination page` value to an XPath query that returns the link you want.

For instance, the following XPath query will match the first link with a class of `grab-me`:

    //a[@class="grab-me"][1]

Here's an XPath query that will match the first link within the very last paragraph of your post:

    //p[position()=last()]/a[1]

For more XPath (and XQuery) syntax examples, refer to the [XPath specification at the W3C](http://www.w3.org/TR/xpath/). If you're a developer, you may also find several [XPath tools](https://developer.mozilla.org/en/XPath#Tools) helpful.

Additionally, this plugin allows you to set a custom `class` value on the `<img>` element that it adds to your post by specifying it in the `Image class value` setting. For maximum compatibility, consider using one of the [WordPress-generated classes](http://codex.wordpress.org/CSS#WordPress_Generated_Classes) most themes utilize. For instance, using `alignright` will probably make the automatically-added image float to the right.

== Installation ==

1. Download the plugin file.
1. Unzip the file into your 'wp-content/plugins/' directory.
1. Go to your WordPress administration panel and activate the plugin.

== Frequently Asked Questions ==

= Will the plugin change my posts, database, or anything else? =

No; this plugin uses [WordPress filters](http://codex.wordpress.org/Plugin_API/Filter_Reference) to make changes on-the-fly. It does not change the content of your posts in any way, and it uninstalls cleanly, without leaving a trace. :)

= Does the plugin save the images or offer any caches? =

No, not at this time, but I'm hoping to add this optional capability to future versions of the plugin. ([Patches welcome](http://github.com/meitar/wp-auto-image-grabber/issues).)

== Screenshots ==

1. The WP-Auto Image Grabber plugin options.

== Changelog ==

= 0.1 =
* Initial development version.

== Other notes ==

This plugin uses [PHP5's DOMDocument methods](http://www.php.net/manual/en/book.dom.php) to parse both your post and the remote page. It uses [XPath](http://en.wikipedia.org/wiki/XPath) to query the DOM.
