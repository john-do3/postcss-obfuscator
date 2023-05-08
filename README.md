<a href="#Intro" title="Section Intro">Intro</a>➤<a href="#Motivation" title="Section Motivation">Motivation</a>➤<a href="#Features" title="Section Features">Features</a>➤<a href="#Installation" title="Section Installation">Installation</a>➤<a href="#Usage" title="Section Usage">Usage</a>➤<a href="#Configuration" title="Section Configuration">Configuration</a>➤<a href="#Extras" title="Section Extra">Extra</a>➤<a href="#Releases" title="Section Releases">Releases</a>➤<a href="#Contributing" title="Section Contributing">Contributing</a>

# :space_invader: PostCSS Obfuscator

- :date:**05-05-2023** :pushpin:**Beta Version 1.5.0**
- :computer:<a href="https://github.com/n4j1Br4ch1D" target="_blank" title="NajibRachid: Agile full-stack developer">NajibRachid</a> :purple_circle:<a href="https://anmoonweb.com/?ref=postcss-obfuscator" target="_blank" title="ANMOON: Right talents at the right place ">ANMOON</a> :office: <a href="https://x-hub.io/?ref=anmoon-postcss-obfuscator" target="_blank" title="XHUB: For Developers By Developers">XHUB</a>

PostCSS plugin that helps you protect your CSS code by obfuscating class names and ids. with customizable configuration.

This plugin provides obfuscation capabilities to your CSS files by replacing class and id selectors with prefixed, simplified or randomly generated strings. This can help to protect your CSS code from reverse engineering and unauthorized copying, while also reducing the file size of your CSS files. plugin offers advanced customizable configuration.

<div style="display:flex">
<img src="https://raw.githubusercontent.com/n4j1Br4ch1D/postcss-obfuscator/main/assets/postcss-obfuscator.png" alt="postcss-obfuscator cli" height="300" width="400">
<img src="https://raw.githubusercontent.com/n4j1Br4ch1D/postcss-obfuscator/main/assets/json-obsfuscation.png" alt="json-Obfuscation" height="300" width="400"/>
<img src="https://raw.githubusercontent.com/n4j1Br4ch1D/postcss-obfuscator/main/assets/css-obsfuscation.png" alt="css-Obfuscation" height="300" width="400"/>
<img src="https://raw.githubusercontent.com/n4j1Br4ch1D/postcss-obfuscator/main/assets/html-obsfuscation.png" alt="html-Obfuscation" height="300" width="400"/>
<img src="https://raw.githubusercontent.com/n4j1Br4ch1D/postcss-obfuscator/main/assets/react-obsfuscation.png" alt="react-Obfuscation" height="300" width="400"/>
</div>

---

## Motivation

- Protecting Intellectual Property, Licensing and Distribution: make it hard for others from stealing your design or using it without your permission.
- Protect against Web scraping, data mining or any malicious activities like stealing data or content: make it hard extracting data from websites automatically using software tools, which use class names & ids.
- Minfiy Your code even more: obsfucation/uglify can slightly reduce file size and improve its performance.

## Features

- [x] No 3rd parties, Dependencies. Just vanilla Nodejs code.
- [x] Quicker then you think.
- [x] Postcss plugin, hence its intended to work with any build tool or task runner.
- [x] Advanced Customizable configuration (Control is yours).
- [x] Supports all files: .html, .js, .php, .vue, ... you name it.
- [x] Supports a wide range of CSS frameworks (Tailwidcss, bootstrap, Bulma, ...).

## Installation

```sh
# npm
npm install postcss-obfuscator --save-dev
```

```sh
# yarn
yarn add postcss-obfuscator --dev
```

## Usage

First, you need to add postcss-obfuscator to your PostCSS configuration. For example, if you're using postcss-cli, you can add it to your `postcss.config.js` file:

```js
//postcss.config.js / postcss.config.cjs
module.exports = {
  // other plugins
  plugins: [
    require("postcss-obfuscator")({
      /* options */
    }),
  ],
};
```

## Configuartion

The plugin has several options that you can configure to customize its behavior. Here are the available options:
**Here's the default donfiguration:**

```js
const defaultOptions = {
  enable: true, // Enable plugin
  length: 5, // Random  name length.
  classMethod: "random", // 'random', 'simple', 'none' obfuscation method for classes.
  classPrefix: "", // ClassName prefix.
  classSuffix: "", // ClassName suffix.
  classIgnore: [], // Class to ignore from obfuscation.
  ids: false, //  Obfuscate #IdNames.
  idMethod: "random", // 'random', 'simple', 'none' obfuscation method for ids .
  idPrefix: "", // idName Prefix.
  idSuffix: "", // idName suffix.
  idIgnore: [], // Ids to ignore from obfuscation.
  indicator: null, // Indicator used to replace names.
  jsonsPath: "css-obfuscator", // Path and Name where to save obfuscation data.
  srcPath: "src", // Source of your files.
  desPath: "out", // Destination for obfuscated html/js/.. files.Be careful using the same directory as your src(you will lose your original files).
  extensions: [".html"], // Extesnion of files you want osbfucated ['.html', '.php', '.js', '.svelte'].
  htmlExcludes: [], // Files and paths to exclude from html obfuscation replacement.
  cssExcludes: [], // Files and paths to exclude from css obfuscation.
  fresh: false, // Create New obfuscation data List or use AlreadyExistedOne (to keep Production Cache or prevent data scrapping).
  multi: false, // Generate obsfucated data file for each css file.
  differMulti: false, // Generate differnt Raandom names for each file.
  formatJson: false, // Format obfuscation data JSON file.
  showConfig: false, // Show config on terminal when runinng.
  keepData: true, // Keep or delete Data after osbfucation is finished?
  callBack: function () {}, // Callback function to call after obfuscation is done.
};
```

- **`enable:`** Enable plugin, **default is true.**
- **`length:`** Random name length for both ids and classes, **default is 5.**
- **`classMethod:`** Obfuscation method for classes, options are: 'random', 'simple', 'none'. 'simple' will remove pronounced vowels and digits, 'none' will keep original name in case you want to just use prefixes or suffixes. **deafult is 'random'.**
- **`classPrefix:`** Prefix for class names, **default is nothig.**
- **`classSuffix:`** Suffix for class names, **default is nothig.**
- **`classIgnore:`** Array of classes to ignore from obfuscation. **deafult is none.**
- **`ids:`** Enable id Obfuscation, **default is false.**
- **`idMethod:`** Obfuscation method for ids, options are: 'random', 'simple', 'none', \__deafult is 'random'._
- **`idPrefix:`** Prefix for id names, **default is nothig.**
- **`idSuffix:`** Suffix for id names, **default is nothig.**
- **`idIgnore:`** Array of ids to ignore from obfuscation. **deafult is none.**
- **`indicator:`** Indicator used to replace names. **default is none.**
- **`jsonsPath:`** Path and Name where to save obfuscation data **default is: css-obfuscator.**
- **`srcPath:`** Path for your source files, **default is: src.**
- **`desPath:`** Destination Path for obfuscated html/js/.. files. Be careful using the same directory as your src(you will lose your original files). **default is: out**.
- **`extensions:`** Extesnions Array of files you want osbfucated ['.html', '.php', '.js', '.svelte'], **default is '.html'.**
- **`htmlExcludes:`** Files and paths to exclude from html obfuscation replacement, **default is none.**
- **`cssExcludes:`** Files and paths to exclude from css obfuscation, **default is none.**
- **`fresh:`** Create New obfuscation data List or use already existed one (to keep Production Cache or prevent data scrapping). **deafult is false.**
- **`multi:`** Generate obsfucated data file for each css file, **default is false.**
- **`differMulti:`** Generate differnt Raandom names for each file, **default is false.**
- **`formatJson:`** Format obfuscation data JSON file, **default is false.**
- **`showConfig:`** Show config on terminal when runinng, **default is false.**
- **`keepData:`** Keep or delete Data after osbfucation is finished? **default is true.**
- **`callBack:`** Callback function to call after obfuscation is done. **default is an empty function**

## npm scripts example

Then npm scripts can be something like this:

```json
"postcss": "postcss src/**/*.css  --dir build",
"postcss:watch": "postcss src/**/*.css --dir build --watch"
"obfuscate": "node postcss-obfuscate",  // for custome script.
```

## Extras

### How it works basicly?

1. Loop over all css files.
2. Uses built-in function(regex) to find classes and ids.
3. Saves Ids & classes in a Json file key represting orginal Names. then genarates random names as values.
4. Creates new folder from source folder.
5. Loops throw files and replaces those keys with values from JSON File.

### Caveats?

- Only CSS is Supported so call the extension After your code was converted to CSS (Example: SCSS to CSS). It's generally better to call it the last.
- One of the best practices is to avoid naming your ids & classes reserved words like HTML element names or attributes. (same for JS & CSS).
- It uses a built-in function to find ids & CSS classes. so it may not work perfectly with advanced CSS selectors.
- I advise `keepData` option as default, and using a different build directory: Using the same directory will replace your files and you may lose original classes and ids names. you will get a warning for that.
- Postcss doesn't support nested directories by default. this is If you intend to work with the plugin's multi-option.

### Destination folder?

Its Better to keep your source files as they are for easy development. Consider specifing another folder for build, if you choose your build directory to be same as source directory you will be replaced and you will loose your orginal files.

### Use indicators?

As mentioned this plugin uses Regex to replace all apperances of classes & ids on files with extension you specify (be it html, cs, js, ...).
Generally if your classes names are unique and avoids reserved keywords, then you got nothing to worry about, otherwise, we got you covered just use the indicator option

```js
   indicator: "@",
```

Now whenever you mention your ids or classes use like this: so it will only replace ones with the indicator around them.

```html
<script>
  let anotherClass = "@anotherClass@";
</script>
<div class="@myClass@">MyClass</div>
```

### Build Static and make production ready?

Postcss usually is runned automatically on `dev` and `build`: so its preferred to create a customer postcss script with the postcss-obfuscator
plugin, a script to run only when you want to obfuscate and to make project ready for production.

```js
//postcss.config.js / postcss.config.cjs
const postcss = require("postcss");
const obfuscator = require("postcss-obfuscator");
// other plugins
postcss([
  obfuscator({
    /* options */
  }),
])
  .process(css)
  .then((result) => {
    console.log("Task Completed!", result);
  })
  .catch((error) => {
    console.error(error);
  });
```

But it can also be done like this:

1.  the `enable` option: to enable it only in specific mode and to make sure tailwindcsss works fine in dev mode:

```js
// process.env.NODE_ENV = "development" //development //obfuscation //production
const isObfscMode = process.env.NODE_ENV === "obfuscation";

//enable: isObfscMode,
```

2.  the `callBack` option, a Callback function to call after obfuscation is done. that way once obfuscation is done you can config and prepare your project for production:

```js
 callBack: function () {
	process.env.NODE_ENV = "production"; // to make sure postcss-obfuscator doesnt re-run.
 },
```

So basically you use `callBack` option to set the env mode back to `production` thus obsfucation will not run, and then config your app source folder to use `out` folder instead of `src` for production.

### Support for css Framworks?

- It's designed to work with CSS, hence its supports any framework you can think of.
- Tailwindcss.
- Bootstrap.
- Bulma.
- ... .

### How To Use With?

#### HTML/CSS:

#### ASTRO/Tailwindcss: <a href="https://github.com/n4j1Br4ch1D/postcss-obfuscator/issues/1" title="postcss-obfuscator">ASTRO/Tailwindcss.</a>

#### React/Vite/Tailwindcss: <a href="https://github.com/n4j1Br4ch1D/postcss-obfuscator/issues/2" title="postcss-obfuscator">React/Vite/Tailwindcss.</a>

## Releases

```txt
  - Initial Version 1.0.0 : 18/02/2023
    - Project Setup.
    - Theory & prove of concept.
  - Initial Version 1.0.3 : 19/02/2023
    - Essential default confugration options (length, jsonPath, placeholder).
    - Settled on a no dependcies solution. built own parser.
    - Developing class finder function.
  - Initial Version 1.0.7 : 20/02/2023
    - Set confugration options.
    - Introduce Id obsfucation.
    - Add prefixers option.
    - Add suffixes option.
  - Initial Version 1.0.9 : 21/02/2023
    - Add srcPath option.
    - Add desPath option.
  - Initial Version 1.1.2 : 21/02/2023
    - Improving class finder method regex.
    - Add showConfig Option.
    - Add formatJson Option.
  - Alpha Version 1.1.5 : 22/02/2023
    - Introducing the Multi option.
    - Refactor & improve code performance.
    - Introduce CLI UI.
  - Alpha Version 1.1.8 : 23/02/2023
    - Introducing the fresh option.
    - Introducing the keepSame option.
    - Adding Logger & logs.
  - Alpha Version 1.2.2 : 24/02/2023
    - Introducing  the callback option.
    - Adding proccess stats/data log.
    - Use a copy method solution.
    - Improve Replace Regex (exclude HTML attributes).
  - Alpha Version 1.2.6 : 24/02/2023
    - Adding Indicator option.
    - deprecate keepSame option.
    - Introduce the differMulti option.
    - Make keepData true as default.
  - Alpha Version 1.3.2 : 25/02/2023
    - Add extensions options.
    - fix differMulti option Bug(class repeation).
    - Deprecate placeholder option.
    - Introducing ExcludeCss option.
    - Introducing ExcludeHTML option.
    - Fix Edge case (Css file count).
  - Alpha Version 1.3.4 : 26/02/2023
    - Fix Files Count (count diffrent extensions).
    - Improve simplify function (add random letter if <1).
  - Alpha Version 1.3.8 : 27/02/2023
    - Add idIgnore/classIgnore Option,
    - Add classMethod option (random/simplify/none).
    - Fix issue (delete data wrong path).
    - Fix bug (Find multiple Ids).
  - Beta Version 1.4.0 : 28/02/2023
    - Improve Exclude Css Option allow Paths.
    - Improve Exclude HTML Option allow Paths.
  - Beta Version 1.4.1 : 01/03/2023
    - Fix Error copying directory: Invalid regular expression: /(?<!</?)\b(sm\:group-hover\)\b(?!=)/: Unterminated
group
  - Beta Version 1.4.2 : 02/03/2023
     - Fix default replacement set default extensions to ['.html'].
  - Beta Version 1.4.5 : 03/03/2023
     - Fix tailwindcss replacement in html (remove backslash escape character before replace).
     - Fix tailwindcss css replacement. (remove dplicated escape charecter before dot "0.5").
     - Fix HTML Exact Match: e.g. (xl:bottom-0 and xl:bottom-0.5).
  - Beta Version 1.5.0 : 05/05/2023
    - Better Documentation(use cases).
    - Better Documentation(build & production).
    - Fine tuning for tailwindcss (#3 Using tailwindcss arbitrary values).
    - Typo folder name css-obfuscator.
  - [Agenda] Beta Version 1.x.x : xx/xx/2023
    - Draft for framework option.
    - Set Indicators Start & End.
    - Fix Files Path (make relative).
    - Add Force option (case: dev env or same Path).
    - Ask before preceding (If dev env or srcPath is desPath).
    - Improve custome script(postcss-obfuscator).
    - Internal Css feature.
    - Refactor tests.

```

## Contributing

Contributions are welcome! If you find a bug or have a feature request, please open an issue on the GitHub repository.

Tests included:

```sh
npm test
```

### License

This project is licensed under the MIT License. See the LICENSE file for more information. Feel free to use it in your own projects, or contribute to its development on GitHub.

**Check Also:** <a href="https://github.com/n4j1Br4ch1D/postcss-prepend" target="_blank" title="postcss-prepend:prepends a comment to the top of your CSS files">PostCSS-prepend</a> | <a href="https://github.com/n4j1Br4ch1D/postcss-mobile-first" target="_blank" title="postcss-mobile-first:converts your desktop-first CSS code to mobile-first CSS code.">PostCSS-mobile-first</a>

**keywords:** _postcss, plugin, obfuscation, css, css classes, class renamer, postcss-rename-selectors, class prefixer, Postcss obfuscator, PostCSS obfuscation plugin, CSS obfuscation, Class name scrambling, CSS security, Obfuscate CSS code, Protect CSS code, Prevent CSS reverse-engineering, tailwindcss, tailwindcss classes list, tailwindcss classes array json, bootstrap, bootstrap classes array json, Scramble HTML classes, CSS anti-theft protection, code privacy, CSS code obfuscator, CSS class name encryption, anti web scraping, Anti-scraping tools, Anti-scraping technology, Web scraping prevention, Web crawling protection._
