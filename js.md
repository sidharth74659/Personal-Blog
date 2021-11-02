# Table of contents

- [To copy a text to clipboard using a one-line javascript code](#to-copy-a-text-to-clipboard-using-a-one-line-javascript-code)
- [Find element taking up extra space (wil add the source link when i find it)](#find-element-taking-up-extra-space-wil-add-the-source-link-when-i-find-it)
- [Single Page Application Routing](#single-page-application-routinghttpsstackoverflowcomquestions52578247single-page-application-routing)
- [Why don’t browsers handle routing for single-page applications?](#why-dont-browsers-handle-routing-for-single-page-applicationshttpsmediumcomgeorgenorbergunderstanding-single-page-application-routing-without-a-library-or-framework-ac781b649995)


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
