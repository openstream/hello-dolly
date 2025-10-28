=== Hello Dolly ===
Contributors: matt
Tags: hello dolly, lyrics, random, admin
Requires at least: 4.6
Tested up to: 6.8
Stable tag: 1.7.3
Requires PHP: 5.6
License: GPLv2 or later
License URI: https://www.gnu.org/licenses/gpl-2.0.html

This is not just a plugin, it symbolizes the hope and enthusiasm of an entire generation summed up in two words sung most famously by Louis Armstrong.

== Description ==

This plugin displays a random lyric from the song "Hello, Dolly" by Jerry Herman in the upper right corner of every WordPress admin page.

The plugin was created by Matt Mullenweg and serves as a demonstration of the basic WordPress plugin structure. It's included with every WordPress installation as an educational example for developers learning to create plugins.

**Features:**

* Displays random lyrics from "Hello, Dolly"
* Appears in the WordPress admin area
* Lightweight and simple implementation
* Demonstrates WordPress plugin development basics

== Installation ==

1. Upload the `hello` folder to the `/wp-content/plugins/` directory, or install the plugin through the WordPress plugins screen directly.
2. Activate the plugin through the 'Plugins' screen in WordPress.
3. Random lyrics from "Hello, Dolly" will now appear in the top right of your admin pages.

== Frequently Asked Questions ==

= What does this plugin do? =

It displays a random lyric from the song "Hello, Dolly" by Jerry Herman in your WordPress admin area.

= Why was this plugin created? =

This plugin serves as a simple example of WordPress plugin development. It demonstrates basic plugin structure, hooks, and WordPress coding standards.

= Can I customize the lyrics? =

Yes! You can edit the plugin file to change or add your own lyrics if desired.

== Changelog ==

= 1.7.3 =
* Fixed WordPress coding standards violations
* Added proper output escaping for security
* Added text domain for internationalization
* Replaced mt_rand() with wp_rand()
* Added GPL license header
* Moved to proper plugin folder structure

= 1.7.2 =
* WordPress 6.4 compatibility

= 1.6 =
* Compatibility with PHP 7.4
* Updated for WordPress 5.3

== Upgrade Notice ==

= 1.7.3 =
This version includes important security improvements with proper output escaping and follows WordPress coding standards.
