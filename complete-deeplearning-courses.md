
```javascript
/* 
Notes:
For 'lessons':
  - search for <ul /> tag within Elements in DevTools
  - identify the one that contains <a /> tags containing similar hrefs as the ones in the lessons array
  - copy and paste the `href` content of the <a /> tags into the lessons array

For 'courseSlug':
  - identify the network request that has similar url as follows: (simply filter by updateLessonProgress)
    - https://learn.deeplearning.ai/api/trpc/course.updateLessonProgress?batch=1
  - copy and paste the `courseSlug` content from the payload of the network request into the courseSlug variable

- run the script in DevTools Console, and voila!

 */

/* 
let lessons = [
  "courses/vibe-coding-101-with-replit/lesson/zwj9r/introduction",
  "courses/vibe-coding-101-with-replit/lesson/rmlc7/principles-of-agentic-code-development",
  "courses/vibe-coding-101-with-replit/lesson/eul8p/planning-and-building-an-seo-analyzer",
  "courses/vibe-coding-101-with-replit/lesson/yuosh/implementing-seo-analysis-features",
  "courses/vibe-coding-101-with-replit/lesson/v9zy5/planning-and-building-a-voting-app",
  "courses/vibe-coding-101-with-replit/lesson/qxitv/enhancing-the-national-parks-voting-app",
  "courses/vibe-coding-101-with-replit/lesson/zl7wo/next-steps-and-best-practices",
];
*/

let courseSlug = "chatgpt-prompt-eng";
let lessons = [
  "courses/chatgpt-prompt-eng/lesson/dfbds/introduction",
  "courses/chatgpt-prompt-eng/lesson/zi9lz/guidelines",
  "courses/chatgpt-prompt-eng/lesson/so7ui/iterative",
  "courses/chatgpt-prompt-eng/lesson/px4pd/summarizing",
  "courses/chatgpt-prompt-eng/lesson/tyucw/inferring",
  "courses/chatgpt-prompt-eng/lesson/ycefn/transforming",
  "courses/chatgpt-prompt-eng/lesson/imsux/expanding",
  "courses/chatgpt-prompt-eng/lesson/jtmdv/chatbot",
  "courses/chatgpt-prompt-eng/lesson/fam6w/conclusion",
];

for (lesson of lessons) {
  updateLessonProgress(lesson, courseSlug);
}

function updateLessonProgress(lesson, courseSlug) {
  // "courses/vibe-coding-101-with-replit/lesson/zwj9r/introduction".split('/')[3]
  const lessonSlug = lesson.split("/")[3]; // Note: this might need some tweaking, so cross-check

  fetch(
    "https://learn.deeplearning.ai/api/trpc/course.updateLessonProgress?batch=1",
    {
      headers: {
        accept: "*/*",
        "accept-language": "en-US,en;q=0.9",
        baggage:
          "sentry-environment=vercel-production,sentry-release=cbf7ff2fbcccbd8744d7e5bb94df1d7acb70e9de,sentry-public_key=2d0e50dc750b22a0023c57845c6ba2ee,sentry-trace_id=e6d0194febac478e958cb7d03bf5c13b",
        "cache-control": "no-cache",
        "content-type": "application/json",
        pragma: "no-cache",
        priority: "u=1, i",
        "sec-ch-ua":
          '"Chromium";v="134", "Not:A-Brand";v="24", "Google Chrome";v="134"',
        "sec-ch-ua-mobile": "?0",
        "sec-ch-ua-platform": '"macOS"',
        "sec-fetch-dest": "empty",
        "sec-fetch-mode": "cors",
        "sec-fetch-site": "same-origin",
        "sentry-trace": "e6d0194febac478e958cb7d03bf5c13b-8747c4ebfafba03c",
      },
      referrer: `https://learn.deeplearning.ai/${lesson}`,
      referrerPolicy: "origin-when-cross-origin",
      body: `{"0":{"json":{"courseSlug":"${courseSlug}","lessonSlug":"${lessonSlug}","status":"completed"}}}`,
      method: "POST",
      mode: "cors",
      credentials: "include",
    }
  )
    .then((res) => res.json())
    .then((data) => console.log(data))
    .catch((err) => console.error(err));
}
```