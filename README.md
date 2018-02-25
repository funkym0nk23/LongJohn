Long John Silveys broken theme

Problem 1 + 2:
The logs when launching stencil state, which stated that it was missing the header folder and file.

{ Error: layouts\header\header.scss doesn't exist!
    at options.error (C:\Users\Miguel\AppData\Roaming\npm\node_modules\@bigcommerce\stencil-cli\node_modules\@bigcommerce\node-sass\lib\index.js:277:32)
  formatted: 'Error: layouts\\header\\header.scss doesn\'t exist!\n        on line 10 of layouts/layouts.scss\n>> @import "header/header";\n   --------^\n',
  message: 'layouts\\header\\header.scss doesn\'t exist!',
  column: 9,
  line: 10,
  file: 'layouts/layouts.scss',
  status: 1 }

To resolve the issue I got a copy of the same version of Cornerstone and copied the folder and file over and bundled the theme and uploaded it to my store
---
Problem 3:

The reason the theme was inverted was caused by a script in footer.html which was rotating the entire theme.

This could be found by navigating the folders by going to these folders:
Templates > components > common > footer.html

Once here the issue starts at line 92 - 102 and here is a copy of the removed script if needed:

 <style>
        body {
           width: 100%;
           height: 100%;
           -moz-transform: rotate(180deg);
           -webkit-transform: rotate(180deg);
           -ms-transform: rotate(180deg);
           -o-transform: rotate(180deg);
           transform: rotate(180deg);
        }
        </style>
