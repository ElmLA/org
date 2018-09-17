# Elm Camp 2018

You will use the [GitHub API](https://developer.github.com/v3/) to create a small front-end application that will take user-supplied input and return a list of GitHub users whose usernames contain the input string.

**NOTE:** The API does allow unauthenticated requests with a rate limit of 10 requests per minute. For the purposes of this exercise, it is acceptable to use the unauthenticated requests (though you are welcome to authenticate your requests as a bonus challenge!).

We will use this project as a way to get you up-to-speed with using Elm. In particular this project will provide opportunities for you to learn about:

- The Elm language and architecture
- Functional programming concepts
- Creating interactive HTML elements
- Making HTTP requests
- Parsing JSON
- Styling with elm-css
- Routing in Elm
- JavaScript interop (stretch)
- ...and more!

# GitHub App specs

This app has three primary states:

1. Landing state with search bar

   <img src="https://emmacunningham.github.io/elm-gh-search/screens/home.png" width="100%" />

2. Display search results of users in response to input submission

   <img src="https://emmacunningham.github.io/elm-gh-search/screens/users.png" width="100%" />

3. Display user's repositories details in response to clicking on a specific user avatar from (2)

   <img src="https://emmacunningham.github.io/elm-gh-search/screens/repos.png" width="100%" />

Per the GitHub API documentation, there are two endpoints that you will need to hit in order to retrieve the data necessary to render the users and their repositories. You do not need to worry about authenticating your requests.

## Features

- Routing for each of the different page views (and the ability to deeplink to any accessible page in the app)
- Error handling / input validation
- Store history of previous searches in [localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Storage/LocalStorage)

## Bonus features!

- Authenticate your requests so you don't need to worry about rate limiting
- Paginating user results

# Resources for learning:

Recommended order of operations for approaching the project:

## Part 1: Get the basic functionality working (est. 1-3 days)

- Get editor set up w/ tools installed
  - [elm-format](https://github.com/avh4/elm-format)
  - Init project: see Derek Cuevas' excellent [elm-webpack-starter](https://github.com/DerekCuevas/elm-boilerplate)
- Start with the basic calculator app in the [Elm lang guide](https://guide.elm-lang.org/architecture/user_input/buttons.html)
- Replace basic calculator w/ input box; on input, should update value stored in the Model
  - Verify that this works by displaying the input value
  - Hint: look at the [elm-lang/html](http://package.elm-lang.org/packages/elm-lang/html/latest/)
- On input submit, make GET request to GitHub API (for users) with search string
  - Look at [elm-lang guide](https://guide.elm-lang.org/architecture/effects/http.html) for an introduction to HTTP requests
  - See [elm-lang/http docs](http://package.elm-lang.org/packages/elm-lang/http/latest)
- Parse JSON response using decoders
  - Use [elm-decode-pipeline](https://github.com/NoRedInk/elm-decode-pipeline)
  - [Elm-seeds video](https://elmseeds.thaterikperson.com/json-decode-pipeline) (8 min)
- Display a list of the top 10 results on the page
  - Remember, things like `div` and `text` are functions! So, you can use them when `map`ping over values, etc.
- For each result, render it as an element that can be clicked on such that on click:
  - Make another GET request to GH API (for repositories of the clicked user)
  - Parse JSON response using decoders
  - Display a list of all of the user's repositories on the page

**_Congrats!!! You've now completed Part 1 (and arguably the hardest part) of Elm Camp!_**

<img src="https://media.giphy.com/media/l3q2zVr6cu95nF6O4/giphy.gif" />

Next, you'll build upon what you already have to add additional functionality.

## Part 2: Add routing (est. 1 day)

- Add routing to your app so that the state of the application persists in the URL:
  - See [this guide](https://www.elm-tutorial.org/en/07-routing/cover.html) on routing
  - home page: `/`
  - user search results: `/users/${username}`
  - user repo page: `/repos/${username}`

## Part 3: Working with JavaScript (est. 1 day)

- Use localStorage (JS API) to persist data across page loads
- Use [ports/subscriptions](https://guide.elm-lang.org/interop/javascript.html) to read/write localStorage from Elm

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
- [Making impossible states impossible](https://www.youtube.com/watch?v=IcgmSRJHu_8) - highly recommend talk about state management using types in Elm **_[before Part 2]_**
- [Reusable dropdown in elm](https://medium.com/elm-shorts/a-reusable-dropdown-in-elm-part-1-d7ac2d106f13) - Explains the Elm way of thinking about "components"
- [Elm bridge](https://elmbridge.github.io/curriculum/) - tutorial w/ a lot of in-depth explanations
- [Elm tutorial](https://www.elm-tutorial.org/en/) - even more in-depth explanations of a lot of concepts in Elm
