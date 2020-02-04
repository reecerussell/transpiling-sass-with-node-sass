# Node Sass
How to transpile S(a|c)ss using NPM. 

## Set up
1. In your project directory, open a command-line and run `npm init`, or for a quick, basic setup run `npm init -y`.
2. Once NPM is setup, install the `node-sass` development dependency by running `npm i -D node-sass`. This installs the `node-sass` package which is used to transpile the s(a|c)ss into standard, browser-readable css.
## Transpile s(a|c)ss
1. Create a new file called `styles.scss`. Then, write some styles, such as:
    ```scss
    body {
        h1 {
            color: #000;
        
            span {
                color: #fff;
            }
        }
        
        p {
            color: red;
        }
    }
    ```
2. Next, in the `package.json`, add a new element in the `scripts` section called `node-sass`. In this script add the command `node-sass styles.scss styles.css`. The new command will take the new file, `styles.scss`, and return the output into a new file called `styles.css`. This looks like: 
    ```json
    "scripts": {
        "node-sass": "node-sass styles.scss styles.css"
    }
    ```
3. Finally, run `npm run node-sass` in the command-line. Once it has completed, a new file called `styles.css` will be created with the transpiled css inside.
4. All Done :)

## Options
`node-sass` comes equiped with many useful options, such as the ability to generate a source map or to minify the css - all of which are easy to implement.
### Source map
To generate a source map for your s(a|c)ss, simply add the `--source-map` argument to your script. For example:
```json
"scripts": {
    "node-sass": "node-sass styles.scss styles.css --source-map"
}
```
### Minification
Similarly to the source map option, to minify the outputted css another argument needs to be added. The new argument is `--output-style`, with the value of `compressed`. For example:
```json
"scripts": {
    "node-sass": "node-sass styles.scss styles.css --output-style compressed"
}
```

There is also the ablilty to use multiple options at once, such as, both the minification and source map. Here is an example:
```json
"scripts": {
    "node-sass": "node-sass styles.scss styles.css --source-map --output-style compressed"
}
```
