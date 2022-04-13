# Code Formatting and Linting for your project

So in this guide we gonna deal with the basic setup for LINTING and CODE FORMATTING in your project.

Quickly the difference between LINTING and CODE FORMATTING:

https://prettier.io/docs/en/comparison.html

Prettier is a classical CODE FORMATTER tool used to automatically format your code on demand (e.g. when saving a file ) to a certain ruleset.

E.g. you have this line here:

```
if( neighbor.longBeard ) {
  console.log("Trim that beard!"
  )}
```

The code formatter will see the syntax of that block is correct, but the formatting is a bit off ;)

So by applying a code formatting you e.g. would get this

```
if( neighbor.longBeard ) {
  console.log("Trim that beard!")
}
```

So a code formatter "tidies up" your code.

But the responsibility of a code formatter ends with the FORMAT (so just the "visuals" of your code, like indentation).

But it will not tell you anything beyong that, e.g. if you have declared variables that you never use. Or imported libraries that you have not installed yet.

For this we need something which is a bit more smart and analyzes your code entirely, to make suggestions how you could clean up things or make your code less prone to errors.

This is where LINTING comes into play.

LINTING will NOT format or change your code automatically like the Code formatter does.

Instead it will just ANALYZE the code and gives you little HINTS what you could do better on individual parts / lines of your code.

E.g. it would tell you that you declared a variable that you never use in your program. It is not a gigantic issue. It could just theoretically confuse your team members who see that variable and have no idea what this is all about. Is it unnecessay? Will you use it in the future? Or was it just an "accident"?

The linter gives you now the chance to rethink your changes, before you commit and push all that nice junk.

All clear until now?

## Focus on setup

So now in this guide we will not focus on WHICH Linting Rules are important to set and which not. Because that is subject to the individual team and their needs & preferences and is covered in a lot of articles on the web.

Instead we just gonna focus on how you can quickly startoff with some sensible defaults.

## Code Formatting

First we gonna setup a tool for automatic code formatting (yes, that one will indeed TOUCH your code and make changes to it)

Setup prettier for VsCode by installing the corresponding extension.

Go to "Extension" in the left icon panel and search for:

`Prettier - Code Formatter`

Now we can apply code formatting within vscode, e.g. when saving or on demand (by a keyboard shortcut).

You can find the shortcut for code formatting in VsCode, when you open to the command bar (CTRL+SHIFT+P) and type "Format". Now you can select & apply the "Format" command on your code.

In case you have no "default formatter" set, please pick Prettier from the arising list.

Alternatively you can configure Prettier to apply formatting on save.

Now please install prettier specific for your project in the terminal (so everybody will use the same version of prettier in the project)

`npm i -D prettier`

Create a config file for prettier in your project:

https://prettier.io/docs/en/configuration.html

E.g. define a .prettierrc.json file.

Experiment with some basic settings from the given page above, e.g. set "singleQuote": false. And then check what happens if you apply code formatting in any javascript file.

Alright!

Now discuss with your team your basic code formatting, e.g. if you wanna have semicolons at the end of each line and how many spaces you wanna use for indentation (2 vs 4)

So far about the basic code formatting setup for your team.

You are now ready to format stuff all the same way.

## Linting

For Linting we gonna use the famous package ESList.

Again we gonna install an extension for usage in VSCode.

Search "ESLint" in the extension menu (from the maintainer Microsoft)

Now we also install eslint into our project, to make sure, every team member uses the same version.

`npm i -D eslint`

Now we can setup an ESLint configuration which matches our project out of the box:

`npx eslint --init`

ESLint will now guide you through a series of questions where you can choose adequate code formatting rules for your given project type.

E.g. you can choose a famous "style guide" (= set of code rules) from a provider like AirBnB.

And then you choose which kind of project you have to activate matching linting rules (Browser JS, React, Node JS)

In the resulting .eslintrc File you can now adapt again settings to your liking by overwriting existing rules in the "rules" object of the config file.

You will have autocompletion within the .eslint file (thanks to the VsCode extension) to grab options.

Checkout the ESLint documentation for all available options:
https://eslint.org/docs/user-guide/configuring/

And now check any of your JavaScript files! 

Chances are ESLint will already detect some issues with your messy stuff and will hightlight that shit brutally ;)

And there you go!

## Final Comments

So in this guide, like mentioned, we will not focus on all the possible options and which concrete settings to apply in your team. There are dozens of articles on this.

Instead let's stress finally on the importante of CODE FORMATTING vs LINTING and the INTERSECTION between both.

Common CONFIGURED CODE FORMATTING rules in your project is an absolute must! Otherwise everyone will reformat any existing code when saving files, causing each time a "change" in your Git Repository on that file!

So it will happen frequently that suddently files will appear as "changed" on your GitHub repository when you do a merge, and often even BIG CHUNKS of codelines, sometimes even the WHOLE (!) file will appear to be changed, even though you just changed one line or maybe no line at all!

What is the reason?

No common code formatting for the whole team!

So please - AT MINIMUM - setup a .prettierrc file for your team where you agree on SEMICOLONS, WHITESPACE and basic formatting of code blocks (e.g. an if block with curly brace on the same line).

Doing this will prevent a lot of headaches due to unnecessary formatting merge conflict.

And about Linting?

Linting for sure is definitely useful to assure common coding practices and give some additional code organisation rules.

This is important to at some point, especially when you do a team project. But compared to Code Formatting this is not an absolute must.

Long story short: Code Formatting is THE #1 absolute priority. Before you do not get a common agreement here, do not deal with Linting.

Once you got your code formatting rules all set, you can go on with your Linting rules.

That's it!

Hope I could have linted & formatted your brain a bit!

Enjoy!
