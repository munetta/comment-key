# comment_keys

Write comments with a specific syntax so that your team members know where to go and what to do. Comments must be written in this syntax

```js
//^*^(your comment here)
```

```js
const comment_keys = require("comment_keys");

const folders = [
  { folder: "./example_1", files: ["wow.js"] },
  { folder: "./example_2", files: [] },
  { folder: "./example_3", files: ["account.js", "bank.js"] },
  { folder: "./example_4", files: "all" },
];

var result = comment_keys(folders);
var comments = result.comments;
var errors = result.errors;

console.log("COMMENTS");
for (let i = 0; i < comments.length; i++) {
  console.log(comments[i]);
}

console.log("ERRORS");
for (let i = 0; i < errors.length; i++) {
  console.log(errors[i]);
}
```

# use case

You are a manager going through all of your files and making updates. You write comments everywhere with the syntax (above) so that when your devs login, they see the list of comments and know where to go and what they need to do. Below each comment you should have a larger comment without the syntax that describes what the problem is in detail.

# how it works

Uses the file system module to traverse a set of directories looking for '//^\*^('. Once '//^\*^(' is found, the comment gets built up and is pushed to the comment set.
