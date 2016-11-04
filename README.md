#Information about SUNET bootstrap theme
Bootstrap with less needs to be downloaded separately.

As far as possible the name on the less files are the same in the SUNET theme as in bootstraps less library.

##Paths
The following paths may have to bee changed:

The path to bootstrap´s less-files (../node_modules/bootstrap/less/bootstrap.less) in less/main.less

The path to the default sprites image file (../img/sprites.png) in the less/mixin/sprites.less

To be able to use the glyphicons the font path (../node_modules/bootstrap/fonts/) in less/variables.less

In the example files the path to bootstraps js-file may have to be changed (it's at the end of all html-files)
and if you don't use the compiled css-file that comes with the example files you may have to change that path (in the head of all html-files)

##How to use
Below I explain new classes and mixins (the explanation can also be found in there files).
In the html example files you can see the SUNET theme in use and explanation on examples on how to use it.

##New mixins and clases
less/mixin/indicator.less :
  Mixin for the small color boxes used in the left menu and in headlines for information boxes
  Default settings are height: 20px and width 20px and default color are the primary color for the site
  Example on how to use (code taken from less/indicator.less)
  ```
    .indicator1 {
        .indicator();
      }
    .indicator2 {
      .indicator(@color: @secondary-color-black);
    }
  ```
less/mixin/sprites.less :
  .sprites is a mixin used to get images from a sprite image file. As default the sprites-file that is used on the
  SUNET main-site is used. To use the mixin whit the default sprites the sprites file path maybe have to be change

  .sprites-bg-pos is a mixin to get the background position of the sprites (can be used on outer things as well)
  To see in use look at the less/footer.less file or less/nav.less file (example code taken from the less/nav.less file)

  ```
    .logo {
      .sprites(@bg-pos-x: -40px; @bg-pos-y: -141px; @h: 48px; @w: 38px);
      position: absolute;
    }
  ```

.no-border new class to remove border is added and used in the less/table.less file

###New classes for the page footer (less/footer.less)
The page footer has a few new classes for example the footer-class that makes the footer look like the footer on sunet.se
.icon is a class for the main settings on the icons in the footer
.icon-worker, .icon-tel, icon-email and icon-map uses the sprites mixin to use the sprite image
.icon-right-text is used for the text on the right side of the icons in the footer (see example in any of the example html-file)

###New classes in the navigation (less/nav.less)
In the header navigation the .logo is new and uses the sprites mixin (for example in use see any of the html example files)
The .nav-stacked is new and used for the left stacked menu (for example in use see the example file index.html)

##Variables (less/variables.less)
Theme color, font and border radius is set in this file. Both new variables and overrides of bootstraps variables.
All colors from the graphic profile is set in this file so it can be used in extended less files.
