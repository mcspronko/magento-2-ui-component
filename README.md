# Simple UI Component example for Magento 2

## Magento DevChannel Overview
This is a series of videos from [Magento DevChannel](https://www.youtube.com/maxpronko) where I best practices when writing the Magento 2 customizations.

## About this Repository
This is an example of simple UI Component in Magento 2 (declaration and JavaScript component). The template file is not mandatory for the UI Component creation.

This repository contains a UI Component which includes:
* Declaration of the UI component with x-magento-init directive

```php
<script type="text/x-magento-init">
   {
       "*": {
           "Magento_Ui/js/core/app": {
               "components": {
                   "pronko-component": {
                       "component": "Pronko_UiComponent/js/component",
                       "title": "Hello World!"
                   }
               }
           }
       }
   }
</script>
```

* JavaScript Component file
```javascript
define([
    'uiElement'
], function(Component) {
    'use strict';

    return Component.extend();
});
```

As a result of this exercise you will render the "Hello World!" text on the content part of every frontend page in Magento 2. This is because we use "default.xml" layout configuration file and "content" container which usually exists on all pages. 

![Magento 2 Home Page with UI Component](https://github.com/mcspronko/magento-2-ui-component/blob/master/docs/simple-ui-component-magento-devchannel.png)

More tutorials at the [Magento DevChannel](https://www.youtube.com/maxpronko).