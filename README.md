# Web stack configuration

Configuration for the following stack:
- next
- tailwindcss
- jest
- react-testing-library
- cypress

I commonly use this stack for projects and it's a breeze to use. The catch is that I always go back to old projects to pick up the configuration I made that worked.

That's what this repo is. It provides:

- TS config for next
- Jest config with react-testing-library and TS
- Cypress config for TS
- Tailwind CSS working with next

## tsconfig.json
Is made to work with next and jest, also has the types for cypress.

## next + tailwind
To use `tailwindcss`, after adding the `postcssconfig.js` and the `tailwind.config.js` you have to have the `pages/_app.tsx` (https://nextjs.org/docs/advanced-features/custom-app)  and import a css file that contains tailwind imports (https://tailwindcss.com/docs/installation/):

```css
@import "tailwindcss/base";
@import "tailwindcss/components";
@import "tailwindcss/utilities";
```

## jest + ts
You need to install `ts-jest` (https://kulshekhar.github.io/ts-jest/user/install).
For tests to work fine (and not complain about jsx and `React` import missing if you're using next). You also need to use `.babelrc`.

## cypress + ts
To have cypress working fine, the current `cypress/tsconfig.json` is what is recommended by the cypress docs (should live on cypress folder). It's types are also present on the root `tsconfig.json` to provide autocomplete.
