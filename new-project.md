## :package: Starting A New GAS Project

**1.** Clone a starting repository and install npm dependencies

```shell
git clone https://github.com/Ecom-Analytics-Co/gas-starter <project_directory>
cd <project_directory>
npm install
```

**2.** Log in to Google clasp and authorize using your Google account.

```shell
npx clasp login
```

Note: this step might change with the resolve of this issue: https://github.com/google/clasp/issues/42

**3.** Create a new "standalone" script project or one bound to a Google Sheet. This step creates the `.clasp.json` file.

```shell
npx clasp create --title "example standalone project" --rootDir ./dist
```

```shell
npx clasp create --type sheets --title "example attached project" --rootDir ./dist
```

More on `create` commands here: https://github.com/google/clasp#create

**4.** Include the necessary OAuth Scopes in the [appsscript.json](appsscript.json) file

**5.** Deploy the project

The `dist` directory contains the bundled code that is pushed to Google Apps Script.

```shell
npm run deploy
```
