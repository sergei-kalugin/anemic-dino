# Wordle Clone

A browser clone of [Wordle](https://www.nytimes.com/games/wordle/index.html), built with React and TypeScript.

## Features

- **Two modes:** the classic 5-letter game and a 6-letter variant.
- **Daily puzzle:** the solution is derived from the current date. The 5-letter mode follows the same daily solutions as the original game.
- **Attempt limits:** 8 attempts in 5-letter mode, 10 in 6-letter mode.
- **On-screen keyboard** alongside physical keyboard input.
- **Share screen** to copy your result.
- **Themes:** light, dark, or adaptive (follows the system setting).
- **Persistence:** game state and settings are kept in local storage.

## Getting started

Requires Node.js and [Yarn](https://yarnpkg.com/) 1.x.

```sh
yarn install
yarn start      # dev server at http://localhost:3000
```

## Scripts

| Command        | Description                                  |
| -------------- | -------------------------------------------- |
| `yarn start`   | Run the dev server                           |
| `yarn build`   | Create a production build in `build/`        |
| `yarn test`    | Run tests in watch mode                      |
| `yarn deploy`  | Build and publish `build/` to GitHub Pages   |

## Project layout

```
src/
  app/              App shell and root component
  wordle_game/      Game screen
  word_tile_grid/   Grid of guesses
  tile/             Single letter tile
  virtual_keyboard/ On-screen keyboard
  header/           Top bar
  help_screen/      About screen
  settings_screen/  Mode and theme settings
  share_screen/     Result sharing
  base/             Shared UI: toast, toggle, theme
  context/          React context exposing the root state
  reducer/          Game state, reducer and helpers
  utils/            Word lists and local storage helpers
```

State lives in a single reducer (`src/reducer/root_reducer.ts`). It tracks the board, keyboard constraints, game mode, theme and toasts. Word lists in `src/utils/` hold the allowed guesses and the possible solutions for each mode.

## Tech stack

- React 19 and TypeScript 5
- Create React App (`react-scripts`) with CSS modules
- Jest and Testing Library
- `gh-pages` for deployment

## Credits

The original game was created by Josh Wardle. This clone is based on the work of [eternalthinker](https://github.com/eternalthinker).
