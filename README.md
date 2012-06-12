#Zend\_Paginator

## Overview

This is a stand-alone, stripped-down version of the official Zend Framework Paginator. The `require_once` statements have been removed so it's possible to use the Paginator without any other component of the Zend Framework.

## Usage

Global configuration can be done using the static methods:

    Zend_Paginator::setDefaultScrollingStyle(new Zend_Paginator_ScrollingStyle_Elastic());
    Zend_Paginator::setDefaultItemCountPerPage(100);
    Zend_Paginator::setDefaultPageRange(3);

If you didn't set a Default ScrollingStyle make sure to pass an instance to `getPages()`:

    $paginator->getPages(new Zend_Paginator_ScrollingStyle_Elastic());

Otherwise the Paginator tries to load the ScrollingStyle with Zend Framework magic which will fail as the other components are missing.

## Symfony

Update your `deps` file:

<pre>
[Zend_Paginator]
    git=git://github.com/Flagbit/Zend_Paginator.git
</pre>

Update your `autoload.php`:

<pre>
$loader->registerPrefixes(array(
    'Zend_Paginator'   => __DIR__.'/../vendor/Zend_Paginator',
));
</pre>