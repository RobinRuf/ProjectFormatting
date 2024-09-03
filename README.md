# Formatting
This repo contains configurations and pre-defined settings to ensure, that the code will be formatted the same, doesn't matter in which IDE the project was coded.

## Dependencies
The only dependency is `prettier`: `npm install --save-dev prettier`

## Supported Editors
- vim
- VSCode
- IntelliJ

## NextJS
If the project is a NextJS (or other fully JS/TS project), you do not need to use `.editorconfig` - only copy and paste the `.prettierrc` and the content in the `package_scripts.json` into the root (`.editorconfig` as new file and the script of `package_scripts.json` in the scripts section of the `package.json` file) of your project.

## Angular (or else) & Java
Insert the `.editorconfig` and `.prettierrc` to the **root** of the project.\
Do this, if you got a **Java Backend** and a **Javascript/Typescript Frontend** like Angular or React.\
The `.prettierrc` will be used for formatting the frontend with additional settings like `bracketSpacing` and the `.editorconfig` will format the frontend and backend for indent rules.

# Auto-Formatting on Save


## VSCode
Confirm, that the Extensions `Prettier - Code formatter` and `EditorConfig for VS COde` are installed.\
In the user settings, set the `editor.formatOnSave` setting to: `"editor.formatOnSave": true`

## IntelliJ
Confirm, that the Plugin `Prettier` is installed and activate the support for `.editorconfig`.\
Go to `Preferences > Languages & Frameworks > JavaScript > Prettier` and be sure, that the path to prettier is correct.\
Activate the option **On code reformat** under **Run for files**.

## Neovim
Install the Plugin `prettier.nvim`, `coc-prettier` or another similar one for the prettier integration.\
Install the Plugin `editorconfig-vim` to give nvim the ability of reading `.editorconfig` files.\
Add an **autocommand** to the `init.lua` file (or for me the `options.lua` file) and create a new one as followed to run prettier automatically while saving the file: `autocmd BufWritePre *.ts,*.html,*.css,*.json,*.md,*.yml :Prettier`

## Run Prettier Command for manual use
To configure a formatting (prettier) command, you need to insert something in the **script section** of your `package.json` file **in the root directory**, not in a subfolder like /frontend.

```json
"format": "prettier --write \"frontend/**/*.{js,jsx,ts,tsx,html,css,json,md}\""
```

> ![NOTE]
> You may need to change the directory of the frontend if needed.

This way, you can use i.e. `npm run format` in your console to run prettier.\
Just be sure you installed `prettier`: `npm install --save-dev prettier`
