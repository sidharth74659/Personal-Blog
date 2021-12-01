# Table of contents

- [To copy a text to clipboard using a one-line javascript code](#to-copy-a-text-to-clipboard-using-a-one-line-javascript-code)
- [Find element taking up extra space (wil add the source link when i find it)](#find-element-taking-up-extra-space-wil-add-the-source-link-when-i-find-it)
- [Single Page Application Routing](#single-page-application-routinghttpsstackoverflowcomquestions52578247single-page-application-routing)
- [Why don’t browsers handle routing for single-page applications?](#why-dont-browsers-handle-routing-for-single-page-applicationshttpsmediumcomgeorgenorbergunderstanding-single-page-application-routing-without-a-library-or-framework-ac781b649995)
- [Find element causing vertical overflow](#find-element-causing-vertical-overflow)

#### To copy a text to clipboard using a one-line javascript code

  ```js
  navigator.clipboard.writeText(text);
  ```

#### Find element taking up extra space (wil add the source link when i find it)

  ```js
  var docWidth = document.documentElement.offsetWidth;

  [].forEach.call(document.querySelectorAll("*"), function (el) {
    if (el.offsetWidth > docWidth) {
      console.log(el);
    }
  });
  ```

#### [Single Page Application Routing](https://stackoverflow.com/questions/52578247/single-page-application-routing)

#### Why don’t browsers handle routing for [single-page applications?](https://medium.com/@george.norberg/understanding-single-page-application-routing-without-a-library-or-framework-ac781b649995)

#### [Find element causing vertical overflow](https://stackoverflow.com/a/60903901)
// Paste the below in the console and scroll. It will log the culprit in the console.

  ```js
  function findScroller(element) {
      element.onscroll = function() { console.log(element)}

      Array.from(element.children).forEach(findScroller);
  }

  findScroller(document.body);
  ```

#### [Finding/Fixing Unintended Body Overflow](https://css-tricks.com/findingfixing-unintended-body-overflow/)

  ```js
  var docWidth = document.documentElement.offsetWidth;

  [].forEach.call(
    document.querySelectorAll('*'),
    function(el) {
      if (el.offsetWidth > docWidth) {
        console.log(el);
      }
    }
  );
  ```
  
  // Ooh! Or you could modify it to outline the offenders in red. Best of both worlds :) (found in comments)

  ```js
  

  javascript:void(function () {var docWidth = document.documentElement.offsetWidth;[].forEach.call(document.querySelectorAll(‘*’), function (el) {if (el.offsetWidth%3EdocWidth) el.style.border = “1px solid red”})})();
  );
  ```

