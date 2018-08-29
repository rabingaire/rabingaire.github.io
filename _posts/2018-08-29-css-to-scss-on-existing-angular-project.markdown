---
layout: post
title: "CSS to SCSS on existing angular 6 project"
date: 2018-08-29 20:26:21 +0545
description: "Learn how to convert styles files from css to scss in existing angular 6 project."
permalink: /css-to-scss-on-existing-angular-project/
---

Recently I was working on angular 6 and I stumbled on a problem when I wanted to change my existing project styles settings from `CSS` to `scss`, I looked over the internet but could not figure out how to change those settings, there are solutions for previous versions but with angular 6 not a clue.

Finally, I figured it out and this is how you can change those settings:

First, go to `angular.json` file on the project and add this object under `schematics`

```json
{
  ...
  "@schematics/angular:component": {
    "styleext": "scss"
  }
  ...
}
```

So after adding this object the `schematics` looks like this:

```json
{
  ...
  "schematics": {
    "@schematics/angular:component": {
      "styleext": "scss"
    }
  }
  ...
}
```

Now when you try to create new components from angular cli it will create a `.scss` file instead of a `.css` file. Other than that if you already had the `.css` file you could manually convert `.css` to `.scss` and point to a right file at `component.ts` by editing `styleUrls` key at `@Component`
Decorator and also angular has global style file inside `src` folder as `styles.css` don’t forget to convert that into `styles.scss` and change all the pointers to `styles.css` into `styles.scss` on `angular.json` file. Thank you have a great day.
