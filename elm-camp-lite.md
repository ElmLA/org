# Elm Camp Lite

This document is intended to help you get your first Elm app up and running, and to get an overall understanding of how to continue making progress as you learn how to do more with Elm!

By the end of this, you will:

- Have your local development environment set up for writing Elm apps
- Understand the basics of the Elm architecture and language
- Have a sense of how to expand your knowledge by reading the Elm documentation
- Be able to progress to the more advanced [Elm Camp](https://gist.github.com/emmacunningham/426ef4e038ce4203d790c3fe93754add), which builds on the foundation laid here by having you build an application that can make HTTP requests and parse JSON responses

## Let's goooo!

- Get your local dev env set up w/ tools installed
  - [Install elm](https://guide.elm-lang.org/install.html)
  - [elm-format](https://github.com/avh4/elm-format)
  - Init project: see the starter project based on Derek Cuevas' excellent [elm-webpack-starter](https://github.com/ElmLA/elm-boilerplate)
- Start with the basic calculator app in the [Elm lang guide](https://guide.elm-lang.org/architecture/buttons.html)
- Review Elm architecture: how do values get updated within Elm?
- Review [type signatures](https://guide.elm-lang.org/types/reading_types.html) in Elm so you can start reading docs on your own!
- Replace basic calculator w/ input box; on input, should update value stored in the Model
  - Verify that this works by displaying the input value
  - Hint: look at the [elm-lang/html](http://package.elm-lang.org/packages/elm-lang/html/latest/)
- Can you modify your project so that the +/- buttons increment/decrement based on the value inputted in the input box?
  - Note: the input will come in as a String, but you'll need your value as an Int (or maybe a Float!) if you are going to increment/decrement
  - You may want to review the docs on [`Result`](https://guide.elm-lang.org/error_handling/result.html)

**_Congrats!!! You've now completed Elm Camp Lite!_**

<img src="http://2.bp.blogspot.com/-wG-FITJoPpI/TgimOEWTv2I/AAAAAAAAALU/DoA1shM5RMg/s1600/tada128586606523883736.jpg" />

Next, you'll build upon what you already have to add additional functionality.

## Functional programming / type system / Elm lang learning objectives:

- No immutability and reliance on `map`, `foldr`, `filter`, etc. for iteration
- Feel comfortable reading type annotations (e.g. able to read [documentation](http://package.elm-lang.org/packages/elm-lang/core/latest) and understand function type signatures)
- Familiarity with `|>`, currying, `>>`
- Understanding of `Maybe`
- Difference between `type` and `type alias`
- installing Elm packages
- using modules in Elm
- missing `console.log()`? Try [`Debug`](http://package.elm-lang.org/packages/elm-lang/core/latest/Debug)

# Some general resources for learning:

- [Elm style guide](https://github.com/NoRedInk/elm-style-guide)
- [Making impossible states impossible](https://www.youtube.com/watch?v=IcgmSRJHu_8) - highly recommend talk about state management using types in Elm
- [Reusable dropdown in elm](https://medium.com/elm-shorts/a-reusable-dropdown-in-elm-part-1-d7ac2d106f13) - Explains the Elm way of thinking about "components"
- [Elm bridge](https://elmbridge.github.io/curriculum/) - tutorial w/ a lot of in-depth explanations
- [Elm tutorial](https://www.elm-tutorial.org/en/) - even more in-depth explanations of a lot of concepts in Elm
