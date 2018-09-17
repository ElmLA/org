# Elm Camp Lite

This document is intended to help you get your first Elm app up and running, and to get an overall understanding of how to continue making progress as you learn how to do more with Elm!

By the end of this, you will:

- Have your local development environment set up for writing Elm apps
- Understand the basics of the Elm architecture and language
- Have a sense of how to expand your knowledge by reading the Elm documentation
- Be able to progress to the more advanced [Elm Camp](./elm-camp.md), which builds on the foundation laid here by having you build an application that can make HTTP requests and parse JSON responses

## Let's goooo!

- Get your local dev env set up w/ tools installed
  - [Install elm](https://guide.elm-lang.org/install.html)
  - [elm-format](https://github.com/avh4/elm-format)
  - Init project: see the starter project based on [Derek Cuevas'](https://github.com/DerekCuevas/) excellent [elm-0.19-boilerplate](https://github.com/ElmLA/elm-0.19-boilerplate)
- Running the app
  - `npm run dev`
  - Open up `localhost:3000`
  - elm-format will help you format as you go along
  - Compiler errors are usually really helpful! (more on this later)
  - _We do_: `Explore History` tool for debugging state
- Start with the basic calculator app from the [Elm lang guide](https://guide.elm-lang.org/architecture/buttons.html)
  - Review Elm architecture: how do values get updated within Elm?
    - _Your turn_: make the calculator increment/decrement by 5 instead of 1.
    - Elm will require that you cover every possible case in a case statement.
      - _Your turn_: what happens if you comment out one of the branch for the `Increment` message in the update function?
  - Review types in Elm
    - Elm is statically typed; type signatures are optional and can be inferred by the compiler, but they're useful to be explicit about!
    - _Your turn_: What happens if instead of incrementing by an `Int` you try to make your app increment by a `String`?
    - Resource: [Reading type signatures](https://guide.elm-lang.org/types/reading_types.html)
- _We do_: Replace basic calculator w/ input box; on input, should update value stored in the Model
  - Add input box to view
    - We'll use the [`input`](https://package.elm-lang.org/packages/elm-lang/html/latest/Html#input) function from [html/Html](https://package.elm-lang.org/packages/elm-lang/html/latest/Html)
  - Add functionality to input element for handling [`onInput`](https://package.elm-lang.org/packages/elm-lang/html/latest/Html-Events#onInput)
  - On input, update the model with the string input
    - This will require that our model hold more than just the current value of the calculator
      - Create a `Model` type alias to hold both the calulator's current value as well as the current input value
      - This changes a lot for our app! But the compiler can help us identify where we need to update things to accomodate the change in data structure for our model.
    - We also need a new `Msg`
      - Add the new `Msg`
      - Hey look! The compiler new that we added a new `Msg` and it needs to be handled in the `update` function!
  - _Your turn_: add a `text` element that renders the stored input value in the model
- _Stretch your turn (pair with a buddy!)_: Can you modify your project so that the +/- buttons increment/decrement based on the value inputted in the input box?
  - Note: the input will come in as a `String`, but you'll need your value as an `Int` (or maybe a `Float`!) if you are going to increment/decrement
  - You can convert a string to an int... check the `String` docs
  - This will return a `Maybe` (because this conversion may not always be capable of yielding an `Int`!)
    - Joël Quenneville has a great explanation of [`Maybe`](https://robots.thoughtbot.com/maybe-mechanics) (also given as a [talk](https://www.youtube.com/watch?v=43eM4kNbb6c&list=PL-cYi7I913S-VgTSUKWhrUkReM_vMNQxG&t=0s&index=17) at Elm Europe 2018)
    - Hint: check out [`Maybe.withDefault`](https://package.elm-lang.org/packages/elm-lang/core/latest/Maybe#withDefault)

**_Congrats!!! You've now completed Elm Camp Lite!_**

<img src="http://2.bp.blogspot.com/-wG-FITJoPpI/TgimOEWTv2I/AAAAAAAAALU/DoA1shM5RMg/s1600/tada128586606523883736.jpg" />

Next, you'll build upon what you already have to add additional functionality.

## Functional programming / type system / Elm lang learning objectives:

- No mutation of data => using `map`, `foldr`, `filter`, etc. for iteration
- Feel comfortable reading type annotations (e.g. able to read [documentation](http://package.elm-lang.org/packages/elm-lang/core/latest) and understand function type signatures)
- Familiarity with `|>`, currying, `>>` (see [here](https://guide.elm-lang.org/appendix/function_types.html))
- Understanding of [`Maybe`](https://package.elm-lang.org/packages/elm-lang/core/latest/Maybe)
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
