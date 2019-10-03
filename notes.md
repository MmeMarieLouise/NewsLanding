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

- make sure that the Devel module is enabled (for debugging)
- in codebase go to contrib modules and find paragraphs module : www/sites/all/modules/contrib/paragraphs
- check out readme.md
- then open www/sites/all/modules/custom/corp_paragraphs/bundles
- in the terminal run `touch card_promo.inc`
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