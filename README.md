Long John Silveys broken theme

Problem 1:
---
The logs when launching `stencil state`, stated that it was missing the header folder and file as the error message I received is shown below:

``{ Error: layouts\header\header.scss doesn't exist!
    at options.error (C:\Users\Miguel\AppData\Roaming\npm\node_modules\@bigcommerce\stencil-cli\node_modules\@bigcommerce\node-sass\lib\index.js:277:32)
  formatted: 'Error: layouts\\header\\header.scss doesn\'t exist!\n        on line 10 of layouts/layouts.scss\n>> @import "header/header";\n   --------^\n',
  message: 'layouts\\header\\header.scss doesn\'t exist!',
  column: 9,
  line: 10,
  file: 'layouts/layouts.scss',
  status: 1 }``

To resolve the issue I got a copy of the same version of Cornerstone and copied the folder and file over and bundled the theme and uploaded it to my sanbox store.

Problem 2:
---
Checking the product category page, the search page, and other places where the filters apply I noticed the styling was off for the side block containing the filters. Upon further inspection I noticed that this was due to a customization that caused the body to be commented out. This was found in _ Assets > scss > layouts > body > body.scss_ by removing the tags that commented out the body, this issue was resolved. 


Problem 3:
---

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
