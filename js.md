- #### To copy a text to clipboard using a one-line javascript code

  ```js
  navigator.clipboard.writeText(text);
  ```

- #### Find element taking up extra space (wil add the source link when i find it)

  ```js
  var docWidth = document.documentElement.offsetWidth;

  [].forEach.call(document.querySelectorAll("*"), function (el) {
    if (el.offsetWidth > docWidth) {
      console.log(el);
    }
  });
  ```

- #### [Single Page Application Routing](https://stackoverflow.com/questions/52578247/single-page-application-routing)

- #### Why don’t browsers handle routing for [single-page applications?](https://medium.com/@george.norberg/understanding-single-page-application-routing-without-a-library-or-framework-ac781b649995)
