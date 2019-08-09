---
layout: page
title: Best Practices
permalink: /best-practices/home
---

Please read the following pages:

- [Coding Standards](/best-practices/coding-standards)
- [Directory Structure](/best-practices/directory-structure)


## Principles and Best Practices

Code Comments
:  Make code expressive such that it can be easily understood by people. With this, comments can be optional. Comments are still code that need to be maintained. If code is littered with comments, every time the code changes, the corresponding comment needs to be updated. Comment the code to explain a very complicated algorithm (only if code can't be simplified) or to document the reason why the logic is as it is.

Readability > Optimization
: Always write code thinking that someone else (even your future self) will read it. Optimizing early and sacrificing readability might make code unmaintainable and buggy. Follow the general guidelines for proper usage of data structures and best practices of your chosen language when coding. These usually take care of the balance between optimization and readability.

Logical Grouping of Codes
: Encapsulate related codes in blocks by seperating related logic into small methods, grouping together related methods into classes / modules, and lumping together classes into packages / folders.

DRY Principle
: **D**on't **R**epeat **Y**ourself. Always be in the lookout for codes that can be reused somewhee else. Extract them into a shareable class / component / CSS style. Share the details of the extracted code to other developers so that it can be reused. With this, developers should also check if a shareable method / package is already available and use that instead. Also, when adding a new 3rd party library check the list of available libraries in the project first.

DO NOT Hardcode
: Keep in mind that the code you're writing will be deployed somehwere else. In the new environment, the database and other external systems that your code is connected to may be different. Connection details must be placed in environment variables so that the same codebase can be used when deloyed to different environments. 

Use Available Infomration when Debugging
: When something's not working in your code, check the logs first. Do not just gloss over the logs but actually read them. Use tools that will help in debugging. For HTML and JavaScript, use the browser's DOM inspector. Add browser plugins for getting more infomration if necessary.

GMG
: Google is your friend. Most of the answers to your questions are probably online. Improve your google-fu.

Ask the Right Questions
:  If you're still stuck after looking for answers online and trying out different approaches, seek help from other developers. When asking questions, state the problem with proper context. That is, don't assume that the other developer is clairvoyant by just copy pasting the problematic line of code and saying that it does not work. Information like the user story your working on, the other parts of the program before it went to the problematic line of code and **the things that you've already tried** are very important.

Never Stop Learning
: Read a lot. Practice what you read. Share your learnings.


### API

API is still an Interface
: Your users for the API are developers. APIs must be clean and must follow the [general REST guidelines](https://hackernoon.com/restful-api-designing-guidelines-the-best-practices-60e1d954e7c9)

### CSS

1. Never hard code font sizes. Either use `em`, `rem` or the variable from variables.less
2. Never hard code colors. Use a variable from `variables.less`
