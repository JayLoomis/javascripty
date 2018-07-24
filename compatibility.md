# Compatibility

There were big changes to JavaScript in ES6 (2015). Even though they've been around a while.
there are still plenty of people running browsers that aren't compatible.

## How to find compatibility information

You can find extensive compatibility information and market statistics on (https://caniuse.com/).

## Managing compatibility with Babel

Babel is a Node package that converts ES6 scripts into ES5 for compatibility. You have to have
Node (and NPM) installed before you can use it.

1.  Use NPM to create a Node package:

    ```bash
    npm init
    ```
   
2.  Follow the prompts from NPM to define the metadata for your package.

3.  Install the Babel command-line interface:

    ```bash
    npm install babel-cli -D
    ```
    
    The `-D` makes NPM add the dependency to the package definition automatically.
    
4.  Install the Babel preset environment:

    ```bash
    npm intall babel-preset-env -D
    ```

5.  Create a `.babelrc` file in your project's root directory:

    ```bash
    touch .babelrc
    ```

6.  Add this text to the newly created `.babelrc` to define the Babel presets:

    ```
    {
      "presets": ["env"]
    }
    ```

7.  Add a build script to `package.json` (it was created when you initialized in step 1).
    Add the following line to the end of the `scripts` object:
    
    ```
    "build": "babel src -d lib"
    ```
    
    This command transpiles all the JavaScript files in the `src` directory and puts the
    converted versions in the `lib` directory.

8.  Run the build to transpile your code:

    ```bash
    npm run build
    ```
    
