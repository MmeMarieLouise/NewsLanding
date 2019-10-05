# Notes

### Paragraphs README.txt

Paragraph is a module to create paragraphs in your content.
You can create bundles(with own display and fields) as paragraph types.

When you add a paragraph field to your node/entity, you can select the allowed bundles, and when using the field, you can select a paragraph type from the allowed bundles to use different fields/display per paragraph.

This module module might be considered a clone of field_collection (on which it is based), but this module has some advantages:

* Different fields per paragraph bundle
* Using different paragraph bundles in a single paragraph field
* Displays per paragraph bundle

Bundles are exportable with features.

### function hook_preprocess_HOOK : Definition

- This hook allows modules to preprocess theme variables for a specific theme hook.
- It should only be used if a module needs to override or add to the theme preprocessing for a theme hook it didn't define.


#### Paragraph fields

1. title 
1. image 
1. author 
1. news resource label  
1. date published 
1. URL


#### Create a Paragraph in Drupal 7
[ref:](https://www.drupal.org/node/2605424)

- follow the path : structure > paragraph bundles > Add paragraph bundle
- Create required fields for paragraph
- Attach it to the existing page as a drop down option and add the paragraph type to news landing : structure > content types > news landing > manage fields > Paragraph Content > edit
- create a news landing test to check that your paragraph works content > add content > News landing > populate text fields > select your paragraph

#### Preprocessing explained

- data transformation
- get the field data and we want to do something with it
- separation of concerns therefore logic lives outside of template
- Customisation - render arrays (twig consumes them on the webpage)

1. Each paragraph type is defined in hook_theme
1. All preprocessing handled by a class
1. Each paragraph type has a corresponding method
1. Each paragraph type has a corresponding twig template

#### Variable API 

- This module extends the Drupal core variable API that handles persistent variables

#### Write Template Preprocess Function Drupal 7

In Drupal the 'themeable' output allows you to control they way that information is conveyed to the user

The modules pass the information to the themes and then the themes control output.

[ref](https://www.youtube.com/watch?v=UOvxCChgSOU)

- make sure that the Devel module is enabled (for debugging)
- in codebase go to contrib modules and find paragraphs module : www/sites/all/modules/contrib/paragraphs
- check out readme.md
- then open www/sites/all/modules/custom/corp_paragraphs/bundles
- in the terminal run `touch card_promo.inc`
- add php opening tags `<?php`
- add preprocess comments
```
/**
 * @file
 * Functions specific to the 'card_promo' paragraphs_item bundle.
 */

/**
 * Deferred preprocess function for entity.
 */

```




### Introduction to theming in Drupal 7


When a page is created in drupal it outputs default HTML mark up, as the themer I must modify that HTML output to conform to the HTML I need for my design

#### Three steps to Theming

Info files - which are meta data that tell drupal what the theme does and what its name is
Template files (or any file that ends with .tpl.php extension)
Template.php, used to override or replace the variables

#### Structure of theme

The themes that we create are in sites > all > themes. Add your theme dir > MyTheme

The files in your template dir which are optional

- mytheme.info    
- tell drupal what your theme can do  
- Define basic properties for your theme:
   - Name and description
   - css/ js files
   - Features (logo, slogan, search box, etc.)
   - Page regions (left sidebar, right sidebar, header, etc)

**NOTE:** the only 3 required things in a .info file are
1. `name = `
1. `description =`
1. `Core = 7. X` (need to specify the version of drupal that the site is compatible with)

Also should add external links to JS scripts and CSS stylesheets 

themes in drupal are responsible for declaring all of the regions  which are available  for an administrator to place blocks into.
Regions are declared inside a .info file
Declaration of features (which appears as a check box)


Regions are also declared
- Page.tpl.php (control the overall layout of your site)
- Template.php (set variables and override theme functions)


[ref:](https://www.youtube.com/watch?v=dS4JR0BbKO8)

#### Drupal 8 quick start up

- open new repo in gitHub
- mkdir etc
- Install Drupal Virtual Machine in repo dir
- Install Virtual Box
- clone repo into sites dir
- Install Vagrant
- cd into VM dir via terminal, run `vagrant up`

- change admin details with new username and password
- download paragraphs, `vagrant ssh`, manually download zip file, un zip and then move dir to NewsLanding > drupal-vm > drupal > web > modules > contrib. then in path `/var/www/drupalvm/drupal/web` Enable module, run `drush en paragraphs`
- download entity_reference_revisions , `vagrant ssh`, manually download zip file, un zip and then move dir to  ** NewsLanding > drupal-vm > drupal > web > modules > contrib. then in path `/var/www/drupalvm/drupal/web` Enable module, run `drush en entity_reference_revisions
`
