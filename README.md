# Visual Markdown Editor for Kirby CMS 2

[![Release](https://img.shields.io/github/release/jonasdoebertin/kirby-visual-markdown.svg)](https://github.com/jonasdoebertin/kirby-mirrormark/releases)  [![Issues](https://img.shields.io/github/issues/jonasdoebertin/kirby-visual-markdown.svg)](https://github.com/jonasdoebertin/kirby-mirrormark/issues) [![License](https://img.shields.io/badge/license-GPLv3-blue.svg)](https://raw.githubusercontent.com/jonasdoebertin/kirby-mirrormark/master/LICENSE)
[![PayPal](https://img.shields.io/badge/donate-paypal-009cde.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=A5K53LA5YBNW4)
[![Gratipay](https://img.shields.io/gratipay/DieserJonas.svg)](https://gratipay.com/DieserJonas)

**Based on [CodeMirror](https://github.com/codemirror/CodeMirror). Inspired by [MirrorMark](https://github.com/musicbed/MirrorMark).**

This Panel field plugin for [Kirby 2](http://getkirby.com) enables you to use an intuitive and visual markdown editor without any hazzle. Just drop in the plugin and you're good to go!

![Screenshot](https://raw.githubusercontent.com/JonasDoebertin/kirby-visual-markdown/master/screenshot.png)

## Important Note (Please Read)

This extension is free to use on both personal and commercial Kirby powered sites. You don't *have* to pay for it. However, please always keep in mind that developing this extension took place in my spare time (and maybe a little bit of the time I should have spend on other work related things). Up until now, quite some hours have been spent on it.

If you want to support further development of this and future Kirby extensions, please consider [donating a small amount](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=A5K53LA5YBNW4) or [buying something from my wishlist](http://www.amazon.de/registry/wishlist/1PDC5ASLLSD67). **This is especially appreciated whenever you use this extension in a project that you get payed for.**

It is awesome to see how the Kirby community connects and helps out each other.
And while I want to be a valuable part of this connection, I can't afford not asking you for a little bit of support.

Cheers, Jonas

## Installation

### Copy & Pasting

If not already existing, add a new `fields` folder to your `site` directory. Then copy or link this repositories whole content in a new `markdown` folder there. Afterwards, your directory structure should look similar to this:

```
site/
	fields/
		markdown/
			assets/
			markdown.php
```

### Git Submodule

If you are an advanced user and know your way around Git and you already use Git to manage you project, you can make updating this field extension to newer releases a breeze by adding it as a Git submodule.

```bash
$ cd your/project/root
$ git submodule add git@github.com:jonasdoebertin/kirby-visual-markdown.git site/fields/markdown
```

Updating all your Git submodules (eg. the Kirby core modules and any extensions added as submodules) to their latest version, all you need to do is to run these two Git commands.

```bash
$ cd your/project/root
$ git submodule foreach --recursive git checkout master
$ git submodule foreach --recursive git pull
```

## Usage

### Within your blueprints

Using the field in your blueprint couldn't be easier. After installing the plugin like explained above, all you need to do is change the `type` of your text fields to `markdown`.

```
fields:
    title:
        label: Post Title
        type:  text
    text:
        label: Text
        type:  markdown
```

*Fields related part of the blueprint for the setup shown in the screenshot.*

### Within your templates

You don't have to change your templates in order to support this field. Just use content created with this field like any regular `textarea` field:

```html
<article>
	<h1>
		<?php echo $page->title()->html() ?>
	</h1>
	<?php echo $page->text()->kirbytext() ?>
</article>
```

## Options

### toolbar

Show / hide the editor toolbar. Set this to `hide` if you want the toolbar to disappear. Per default, the toolbar will be shown.

```
fields:
    text:
        label:   Text
        type:    markdown
		toolbar: hide
```

### header1 & header2

Specify the header levels to be used with the *H1* and *H2* toolbar buttons (`h1` to `h6`). Defaults to `header1: h1` and `header2: h2`.

```
fields:
    text:
        label:   Text
        type:    markdown
		header1: h2
		header2: h3
```

*If you have any suggestions for further configuration options, [please let me know](https://github.com/JonasDoebertin/kirby-visual-markdown/issues/new).*
