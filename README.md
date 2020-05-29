# MJML Email Boilerplate
A boilerplate for MJML to make developing email templates a breeze.

## 🧘‍♀️ Development server

- Create a `/dist` folder in the root. (sadly otherwise mjml will compile your ile to dist.html...)
- Run `yarn dev` from the root directory

This will run the MJML watch command and outputs your files in the /dist folder.
A simple live-server with hot reloading will be spinned up for the ease of development.


## 🏁 Production build

### Production build for Javascript
To output your HTML email templates in a Javascript bundle you first need to make sure they are all required in `index.ts`. (see below: how to use)

- Run `yarn build:js` from the root directory

This will run a webpack build and compiles all your html files in `bundle.js` in the /dist folder


### Production build for HTML
To output your HTML email templates as minified html files:

- Run `yarn build` from the root directory

This will run a mjml build and builds all your minified html files to the /dist folder


## 🚀 How to use
How to use the javascript import. Which is very useful to use the email templates directly in your backend.
First: Require your templates in our entry file `index.ts`.

Example:
```typescript
import index from './templates/index.mjml'
import login from './templates/login.mjml'
import forgotPassword from './templates/forgotPassword.mjml'

export default {
  index,
  login,
  forgotPassword,
}

```

__Use a template__

Require the templates from the email folder.  Import path may differ depending on your implementation and where you put the emails folder.

If your using yarn workspaces for example it can be done as follows:

```typescript
import { index, login, forgotPassword } from '@mjml-email-boilerplate'

sendEmail(login, { /* my options */ })
```

Good luck and Happy coding 🤓!
