# bootstrap3-glyphicons-pro
How to modify bootstrap3 to integrate the full set of icons from glyphicons pro and keeping existing code compatiblity.

This is a basic how to for now, I'll try to integrate it with bower/gulp later.

I took the orignale files and made some modification with a comment like the following explaining the changes:

    //bootstrap3-glyphicons-pro [Change] from glyphicons-halflings-regular to glyphicons-regular

## How to perform the required changes


1. Buy Glyphicons Pro package at [Glyphicons](http://glyphicons.com/). 
   
   Great work done here, it's not that expensive and add great value to your website
    
2. copy the Glyphicons Pro fonts, files listed below 
    * glyphicons-regular.eot
    * glyphicons-regular.svg
    * glyphicons-regular.ttf
    * glyphicons-regular.woff
    * glyphicons-regular.woff2

    to the following folder of your project

        /client/bower_components/bootstrap-sass/assets/fonts/bootstrap
    
3. Copy the following file from this project 
    
        src/bootstrap-sass/assets/stylesheets/bootstrap/_glyphicons-pro.scss
             
   to your project
   
        /client/bower_components/bootstrap-sass/assets/stylesheets/bootstrap/    
        
4. edit the _variable.scss to change the font name and id

        /client/bower_components/bootstrap-sass/assets/stylesheets/bootstrap/_variable.scss

    * from "glyphicons-halflings-regular" to "glyphicons-regular"
    * from "glyphicons_halflingsregular"  to "glyphiconsregular"
       
  You can check the file shipped within this project
   
    /client/bower_components/bootstrap-sass/assets/stylesheets/bootstrap/_variable.scss
       
5. edit _bootstrap.scss to change the import from */glyphicons"* to */glyphicons-pro"*

You can check the file shipped within this project
       
    /client/bower_components/bootstrap-sass/assets/stylesheets/_bootstrap.scss


## How did I generated the _glyphicons-pro.scss

* I took _glyphicons.scss from bootstrap and changed the font-family to "Glyphicons Regular"
* I've took glyphicons_pro_1_9_2/glyphicons/web/bootstrap_example/css/boostrap.css icon list and reprocess the content using [UltraEdit](https://www.ultraedit.com/) macro 

from this syntax

    .glyphicons-glass:before {
      content: "\E001"
    }
 to the bootstrap3 syntax
 
    .glyphicon-glass                         { &:before { content: "\E001"; } }

 I've also remove the "s" to glyphicons so that the code that was using the halflings version still work.
 
 