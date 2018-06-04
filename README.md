# JSDoc Chameleon Template
Chameleon is a nice, modern JsDoc 3 template for better looking documentation pages! [https://github.com/layoutzweb/jsdoc-modern-template](https://github.com/layoutzweb/jsdoc-modern-template).

This template is a fork of the [Minami Js Doc Template](https://github.com/nijikokun/minami) with a few tweeks, it is fully responsive and gives you a customization options to choose colors and fonts to make it look as close to your brand as possible.

##### Github Repo [https://github.com/layoutzweb/jsdoc-modern-template](https://github.com/layoutzweb/jsdoc-modern-template) 
![Modern JS Doc Template Screenshot](https://i.imgur.com/8xc5ehY.jpg)
![LayoutzWeb JSDoc Chameleon Template Screenshot](https://i.imgur.com/w0UzHwy.jpg)

## Usage
Clone repository to your designated `jsdoc` template directory, then:

### Node.js Dependency
In your projects `package.json` file add a generate script:

```json
"script": {
  "generate-docs": "node_modules/.bin/jsdoc -c .jsdoc.json -d docs --verbose"
}
```
The ```-c``` option points to a config file, path relative to your package.json file
The ```-d``` options tells with directory to save the generated files

In your `jsdoc.json` file (create one in the root of your project if you don't have one), add a template option.

```json
"opts": {
  "template": "node_modules/jsdoc-chameleon-template"
}
```

## Style Switcher
The Style Switcher is a simple pop up to help you visualise different color and font configurations. To enable the style switcher first take a look at the example configuration in the bottom of this page. Notice it has a key ```styleSwitcher``` and a couple of others, the ```colors``` keys, it has all the available default color schemes and you can add yours in case none of the default ones fit's your needs, and the ```fonts``` key, which has all the avavilable fonts and just like with colors, you can choose more fonts from [Google Fonts](https://fonts.google.com/) and add to the list.
To enable and use it follow these steps:
* Setting the ```styleSwitcher:true``` in your jsdoc.json
* Re-generate your docs by running the ```generate-docs``` command
* Visit your documentation page
* Select your scheme and fonts
* Click the export button on the style switcher
* Copy your configuration to your ```jsdoc.json``` file


## Adding Search
If you would like to enable [Algolia DocSearch](https://community.algolia.com/docsearch/), you can pass a `search` object into the `templates` object.

```json
"templates": {
    "search": {
        "apiKey": "your-api-key",
        "indexName": "Your index name. Defaults to braintree.",
        "hitsPerPage": "Number of Results to show. Defaults to 7.",
    }
}
```


### Example JSDoc Config
```json
{
  "tags": {
    "allowUnknownTags": true,
    "dictionaries": ["jsdoc", "closure"]
  },
  "source": {
    "include": ["package.json", "README.md"],
    "exclude": ["./src/docs"],
    "excludePattern": "(node_modules|__tests__|__mocks__|^|\\/|\\\\)_"
  },
  "plugins": [
    "plugins/markdown",
    "src/docs/plugins/meta"
  ],
  "recurseDepth": 2,
  "template": {
    "title": "Postman SDK - An easy way to integrate sharing documentation and more into your development environment",
    "shortTitle": "Postman SDK",
    "logo": "https://github.com/layoutzweb/postman-sdk/raw/master/media/postman-logo.png",
    "links": [
      {"github": "https://github.com", "title": "View it on Github"},
      {"npm": "https://github.com", "title": "View it on NPM", "size": 19}
    ],
    "scheme": "0",
    "disableSort": false,
    "font": {
      "titleFont": "Roboto",
      "textFont": "Roboto",
      "codeFont": "Roboto Mono"
    }
  },
  "styleSwitcher": true,
  "colors": [
    {
      "text": {
        "primary": "#dcdcdc",
        "contrast": "#f78200"
      },
      "background": {
        "primary": "#282c34",
        "contrast": "#1d2027"
      }
    },
    {
      "text": {
        "primary": "#dcdcdc",
        "contrast": "#5ebd3e"
      },
      "background": {
        "primary": "#282c34",
        "contrast": "#1d2027"
      }
    },
    {
      "text": {
        "primary": "#dcdcdc",
        "contrast": "#ffb900"
      },
      "background": {
        "primary": "#282c34",
        "contrast": "#1d2027"
      }
    },
    {
      "text": {
        "primary": "#dcdcdc",
        "contrast": "#e23838"
      },
      "background": {
        "primary": "#282c34",
        "contrast": "#1d2027"
      }
    },
    {
      "text": {
        "primary": "#dcdcdc",
        "contrast": "#009cdf"
      },
      "background": {
        "primary": "#282c34",
        "contrast": "#1d2027"
      }
    }
  ],
  "fonts": {
    "text": "Alegreya+Sans|Alfa+Slab+One|Bangers|Bungee|Changa+One|Exo|Fira+Sans|Heebo|IBM+Plex+Sans|Lalezar|Lato|Open+Sans|Oswald|PT+Sans|Passion+One|Patua+One|Questrial|Raleway|Righteous|Roboto|Rubik|Source+Sans+Pro|Squada+One|Titillium+Web|Voces",
    "code": "Cousine|Cutive+Mono|IBM+Plex+Mono|Inconsolata|Nanum+Gothic+Coding|Oxygen+Mono|PT+Mono|Share+Tech+Mono|Source+Code+Pro|Ubuntu+Mono|VT323"
  },
  "opts": {
    "destination": "./docs/",
    "encoding": "utf8",
    "private": false,
    "template": "./src/docs/jsdoc-template"
  }
}
```

## License

Licensed under the Apache2 license.
