# Magento 2 UI Component Module example

## Overview
The Magento 2 Module provides an example of a simple UI Component. The UI Component usually includes a JavaScript part and a template (HTML) part. The example provided consists only JavaScript part. There is no separate HTML template component as the template for the UI Component is declared as part of PHTML template. The module has been created as part of the Magento DevChannel video tutorials.

## Magento DevChannel Overview
[Magento DevChannel](https://www.youtube.com/maxpronko) is a YouTube channel created by Max Pronko. It provides the series of videos with the best practices for customizing Magento 2 platform.

## Video Tutorial
You can watch the video "[Creating Simple UI Component in Magento 2 - Max Pronko (4K)](https://www.youtube.com/watch?v=3S0bA87p_gI)" with the steps on how to create the simple UI Component in Magento 2

[![Creating Simple UI Component in Magento 2 - Max Pronko (4K)](https://img.youtube.com/vi/3S0bA87p_gI/0.jpg)](https://www.youtube.com/watch?v=3S0bA87p_gI)

## Installation

### Requirements
1. Magento 2.1 or Magento 2.2
2. PHP 7.0+

### Modman
Use modman to clone the repository into your Magento 2 project. From the Magento 2 root directory execute the following command:
```bash
$ modman clone git@github.com:mcspronko/magento-2-ui-component.git
```

This is my preferable way of installing a Magento 2 module if I want to perform code changes.

### Composer
Add the repository into a composer.json file. From the Magento 2 root directory execute the following commands:
```bash
$ composer config repositories.mcspronko vcs https://github.com/mcspronko/magento-2-ui-component
$ composer require mcspronko/magento-2-ui-component:dev-master
```
### Install the Module
Enable the Pronko_UiComponent module:
```bash
$ bin/magento module:enable Pronko_UiComponent
```

Run setup:upgrade command:
```bash
$ bin/magento setup:upgrade
```

## About this Repository
This is an example of a simple UI Component in Magento 2. It consists of a UI Component declaration and JavaScript Component minimum logic required for a UI Component. The template file is not mandatory for the UI Component creation.

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
