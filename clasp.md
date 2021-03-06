## Clasp Files Guide

### appsscript.json file

#### "Manifest updated. Do you want to overwrite?"

```shell
? Manifest file has been updated. Do you want to push and overwrite?
```

If you see a prompt like the above:

1. Say yes
2. Open the script on script.google.com (refresh if already opened) or use `clasp open`
3. Under project settings make sure `Show "appsscript.json" manifest file in editor` is checked
4. Go to the scripts editor on script.google.com and under Files open `appsscript.json`
5. Copy the contents of `appsscript.json` into your local [appsscript.json](appsscript.json) file

Note that this warning may show sometimes when an insignificant change, like formatting, is made

#### Example minimal appsscript.json

```json
{
  "timeZone": "America/New_York",
  "runtimeVersion": "V8",
  "dependencies": {},
  "exceptionLogging": "STACKDRIVER"
}
```

#### Example webapp appsscript.json

```json
{
  "timeZone": "America/New_York",
  "runtimeVersion": "V8",
  "dependencies": {},
  "exceptionLogging": "STACKDRIVER",
  "webapp": {
    "executeAs": "USER_DEPLOYING",
    "access": "ANYONE_ANONYMOUS"
  }
}
```

More info: [Apps Script: Manifest structure](https://developers.google.com/apps-script/manifest)

#### OAuth Scopes

You can set scopes explicitly in the [appsscript.json](appsscript.json) `appsscript.json` under the `oauthScopes`
top-level field. The "oauthScopes" field specifies an array of strings.

```json
{
  "...": "...",
  "oauthScopes": [
    "https://www.googleapis.com/auth/spreadsheets.readonly",
    "https://www.googleapis.com/auth/youtube.upload"
  ]
}
```

More info: [Apps Script: Authorization Scopes](https://developers.google.com/apps-script/concepts/scopes)

Complete list of OAuth scopes: [OAuth 2.0 Scopes for Google APIs](https://developers.google.com/identity/protocols/oauth2/scopes)

### .clasp.json file

When running clone or create, a file named .clasp.json is created in the current directory to describe clasp's
configuration for the current project.

#### Example minimal .clasp.json

```json
{
  "scriptId": "123WgD6FBS2bGsPMQF...Z2tcYeQpExK_xuQ5rabc",
  "rootDir": "dist/"
}
```

#### Example advanced .clasp.json

```json
{
  "scriptId": "123WgD6FBS2bGsPMQF...Z2tcYeQpExK_xuQ5rabc",
  "rootDir": "dist/",
  "projectId": "project-id-xxxxxxxxxxxxxxxxxxx",
  "fileExtension": "ts",
  "filePushOrder": ["file1.ts", "file2.ts"]
}
```

More info: [Project Settings File (.clasp.json)](https://github.com/google/clasp#project-settings-file-claspjson)

### .claspignore file

The `.claspignore` file allows you to specify file and directories that you do not wish to not upload to your Google
Apps Script project via `clasp push`.

The default `.claspignore` file in the Apps Script Starter kit will push all the JS and HTML inside the `rootDir` folder
and ignore all the other files.

More info: [Ignore File (.claspignore)](https://github.com/google/clasp#ignore-file-claspignore)

---

## TypeScript

See [clasp/docs/typescript.md](https://github.com/google/clasp/blob/4464f73465dd9697ae22fab81c42370ca98232c6/docs/typescript.md)
