[![Build Status](https://travis-ci.org/cssjanus/php-cssjanus.svg?branch=master)](https://travis-ci.org/cssjanus/php-cssjanus) [![Latest Stable Version](https://poser.pugx.org/cssjanus/cssjanus/v/stable.svg)](https://packagist.org/packages/cssjanus/cssjanus)

# CSSJanus

Convert CSS stylesheets between left-to-right and right-to-left. This is a PHP port of [CSSJanus](https://code.google.com/p/cssjanus/) (written in Python).

## Basic usage

```php
$rtlCss = CSSJanus::transform( $ltrCss );
```

## Advanced usage

``transform( $css, $swapLtrRtlInURL = false, $swapLeftRightInURL = false )``

* ``$css`` (string) Stylesheet to transform
* ``$swapLtrRtlInURL`` (boolean) Swap 'ltr' and 'rtl' in URLs
* ``$swapLeftRightInURL`` (boolean) Swap 'left' and 'right' in URLs

### Preventing flipping

Use a ```/* @noflip */``` comment to protect a rule from being changed.

```css
.rule1 {
  /* Will be converted to margin-right */
  margin-left: 1em;
}
/* @noflip */
.rule2 {
  /* Will be preserved as margin-left */
  margin-left: 1em;
}
```

## Main repository

The main repository is the JavaScript version, [node-cssjanus](https://github.com/cssjanus/node-cssjanus).  Pull requests, feature requests, and bugs should be submitted there when they relate
to the actual CSS transformation or test cases of it.  Implemented changes will then be ported here.
