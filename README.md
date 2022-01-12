# FontAwesomeMendix
Font Awesome module for use in Mendix projects

## Installation

Add the module to your project through the Mendix Marketplace. 

For advanced options, import the fontawesome stylesheet into your custom stylesheets:

```
@import "../../fontawesome/web/fontawesome.scss";
```

## Using FontAwesome classes

Once you import the module, you can use FontAwesome classes to add icons to containers.

##### Example

Add classes `fas` and `fa-plus` to an empty Mendix container. You should see the plus icon appear when you run the project. 

# Advanced options

If you have imported the FontAwesome stylesheet as described above, you can use the advanced options.

## Using FontAwesome on buttons

The FontAwesome stylesheets by default overrides some styling on buttons allowing you to add FontAwesome classes to buttons. If FontAwesome is interfering with your existing styling rules, exclude this behavior by configuring the following variable before importing the stylesheet:

```
$override-core: false;
```

## Overriding glyphicons

You can overwrite glyphicons with FontAwesome icons. This requires a configuration each time you want to overwrite a specific icon. 

Overwrite glyphicons by calling the fa-replace-glyphicon mixin

```
.glyphicon {
    @include fa-replace-glyphicon("plus", $fa-var-plus);
    @include fa-replace-glyphicon("pencil", $fa-var-pencil);
}
```

## Including FontAwesome icons in styling

You can also add FontAwesome icons outside of glyphicon scope. You can call the `fa-include-icon` mixin like so:

```
@include fa-include($fa-var);
```

This will add all necessary styling to add an icon for that class

#### Mixin parameters

You can call the mixins with the following parameters:

* **Glyphicon name**: The glyphicon name, this should be the classname of the glyphicon that Mendix adds to an element
* **FontAwesome variable**: The FontAwesome variable name. This should be available in your editor context, so autofill is possible
* **Weight**: Optional font-weight (400 or 900)
* **Size**: Optional font-size parameter

## Further reading

Refer to the [FontAwesome documentation](https://fontawesome.com/) to discover icons