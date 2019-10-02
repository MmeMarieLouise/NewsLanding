# Notes

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

#### Write Template Preprocess Function Drupal 7

- in codebase go to contrib modules and find paragraphs module : www/sites/all/modules/contrib/paragraphs
- check out readme.md
- 