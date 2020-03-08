# Fixed-product-image-on-page-scroll.-Debut-theme-Solved


Here is a step by step short tutorial on how to fix the left product image in Debut theme.


1- Click on online store => actions => edit code => theme.scss.liquid
2- in the line 2638, remove the following line  (Note: if you have modified your theme.scss.liquid, you may fin this code in a different line)

overflow: hidden;
 

 

 

 

3- at the very bottom of the code paste the following code :

div.sticky {
    position: -webkit-sticky;
    position: sticky;
    top: 0px;
    z-index: +1; 
@include media-query($small) {
 position: relative;
      top: 0px;
  }  
}
4- Now open product-template.liquid and go to the line 43 which looks like this and remove it

<div class="grid__item product-single__photos {{ product_image_width }}{% if section.settings.image_size == 'full' %} product-single__photos--full{% endif %}">
5- Paste this code instead 


    <div class="sticky grid__item product-single__photos {{ product_image_width }}{% if section.settings.image_size == 'full' %} product-single__photos--full{% endif %}">
Click save ! And it should work
