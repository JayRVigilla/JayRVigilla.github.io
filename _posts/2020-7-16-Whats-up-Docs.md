---
layout: post
title: What's up Docs?
---

Near the end of coding boot camp, we were giving Lightning Talks in class. They're five to seven-minute presentations about a technology/library/what-have-you. Everyone had prepared to answer questions. One of my classmates _didn't_ ask for questions. Instead, he said: "I'd like to leave the floor open for questions, but you're Engineers so just read the docs first." We all laughed and cheered the chutzpah to say such a thing... then today happened and I am laughing at myself humbled and hopefully wiser.

I had mentioned before that I was working on a takehome project for a job interview. Well, I thought that I was doing my due diligence by diving into research online about the libraries that were new to me that I was asked to use (`Redux-Saga`, `Reselect`). I downloaded the app template (React Boilerplate) and started trying to write code to match the patterns I saw in YouTube tutorials.

I write code with VS Code and searched for one of the methods I had used, only to see it was popping up in other files that I hadn't touched yet. Was it possible this boilerplate had these libraries built into it already? Yup. And guess what? There was a folder of doc files describing how to use the libraries with links to the resources. If only I had read the docs, it would have saved me some time.

Just now I put a little time on my side project: the CoverLetterMaker() app. After the first two days, I was hitting a wall. I'm writing a Node.js app that accesses my local file system, so using the fs library made sense. I was able to read and log a file in a given folder using `fs.readFile()`. The next step is to save each file to a variable. I was blocked the other night when `fs.readFile()` would return undefined. Guess who read the docs on `fs.readFile(`) and realized that it's an async function? This guy!

Sidebar for those that don't code. What's an async function? I think of functions as recipe instructions. Functions are steps taken to an expected output that can be reused or repeated. You can reuse the same recipe for your Sunday morning waffles. In most cases, code is synchronous: it does not move on to the next step until the last one is complete. Async is "asynchronous." That's like when you're baking and you see the first step is to preheat the oven. You don't turn on the oven, sit and wait for it to reach the temperature, and then start mixing ingredients. Instead, you crank the oven and do the rest of the recipe.

Back to the CoverLetterMaker() story. When I read the docs on `fs.readFile(`) it realized that it didn't return the data from the file it was reading. The file was just sitting there after having been read, like a coffee table book no one bothers to commit any of the contents to their own memory. However, `readfileAsync()` returns the value. So I can now save the files to variables and move forward on this side project... but tomorrow. It's getting late.

The moral of these stories is this: read the docs. Don't start looking everywhere else for the answers before you familiarize yourself with the basics. Sometimes they're baked right in.