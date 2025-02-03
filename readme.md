To automate Prettier for your project, you can follow these steps:

1. **Install Prettier**: First, you need to install Prettier as a development dependency in your project.

   ```bash
   npm install --save-dev prettier
   ```

2. **Create a Prettier configuration file**: Create a `.prettierrc` file in the root of your project to define your Prettier configuration. For example:

   ```json
   {
     "semi": true,
     "singleQuote": true,
     "tabWidth": 2,
     "trailingComma": "es5"
   }
   ```

3. **Add a Prettier script**: Add a script to your `package.json` to run Prettier.

   ```json
   "scripts": {
     "prettier": "prettier --write ."
   }
   ```

4. **Set up a pre-commit hook**: Use `husky` and `lint-staged` to run Prettier on staged files before each commit.

   ```bash
   npx husky-init && npm install
   npm install --save-dev lint-staged
   ```

   Update your `package.json` to include `lint-staged` configuration:

   ```json
   "husky": {
     "hooks": {
       "pre-commit": "lint-staged"
     }
   },
   "lint-staged": {
     "*.js": "prettier --write"
   }
   ```

5. **Run Prettier**: You can now run Prettier manually using the script you added:

   ```bash
   npm run prettier
   ```

This setup will ensure that Prettier is automatically run on your codebase, keeping your code consistently formatted.
