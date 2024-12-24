
### Export Twitter Bookmarks:

1. First, install the extension from the link: https://github.com/prinsss/twitter-web-exporter?tab=readme-ov-file
2. Then, navigate to `x.com` (formerly Twitter). Once you're there, keep an eye out for a dialog that appears with some interesting content. You might even spot a cute cat peeking from the left side!
3. Now, to collect your bookmarks, simply head to the bookmarks page and run the script provided below. Once all your bookmarks are captured, you can easily export the relevant data. Happy exporting!

```js
// This script scrolls continuously to the end of the page for 2 minutes on X.com (formerly Twitter).
// You can paste this in the console of the browser and run it, it will scroll to the end of the page.

const interval = 100; // Scroll interval in milliseconds
const duration = 2 * 60 * 1000; // Total duration in milliseconds (2 minutes)
let elapsed = 0; // Timer tracker

const scrollToEnd = setInterval(() => {
  window.scrollBy(0, 1000); // Scroll down by 1000 pixels
  elapsed += interval; // Increment elapsed time

  // Stop scrolling after the specified duration
  if (elapsed >= duration) {
    clearInterval(scrollToEnd);
    console.info('Scrolling stopped after 2 minutes.');
  }
}, interval);
```