# FontAwesomeMendix
Font Awesome module for use in Mendix projects

## Installation

Add the module to your project through the Mendix Marketplace. 

## Using FontAwesome classes

You can now use FontAwesome classes to add icons to containers.

#### Example

Add classes `fas` and `fa-plus` to an empty Mendix container. You should see the plus icon appear when you run the project. 

## Overriding glyphicons

If you prefer, you can overwrite glyphicons with FontAwesome icons. This requires a configuration each time you want to overwrite a specific icon. 

Import the functions by adding the following scss to your stylesheets
```
@import "../../fontawesome/web/fontawesome.scss";
```

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