Instant typescript npm packages.

![logo](images/ts-packrat.jpg)

[![Version](https://img.shields.io/npm/v/ts-packrat.svg)](https://npmjs.org/package/ts-packrat)
[![Downloads/week](https://img.shields.io/npm/dw/ts-packrat.svg)](https://npmjs.org/package/ts-packrat)
[![License](https://img.shields.io/npm/l/ts-packrat.svg)](https://github.com/YizYah/ts-packrat/blob/master/package.json)
[![Geenee](https://img.shields.io/badge/maintained%20by-geenee-brightgreen)](https://npmjs.org/package/geenee)

![easy](images/packrat.jpg)

[//]: # ( ns__custom_start toc )
<!-- toc -->
* [:clipboard: Why](#clipboard-why)
* [:bulb: What](#bulb-what)
* [:wrench: How](#wrench-how)
* [:heavy_exclamation_mark: Help](#heavy_exclamation_mark-help)
* [:eyes: See Also](#eyes-see-also)
<!-- tocstop -->

[//]: # ( ns__custom_end toc )

# <a name="clipboard-why"></a>:clipboard: Why
When you create a npm package, you shouldn't have to worry about anything but writing your TS code.

# <a name="bulb-what"></a>:bulb: What
Your package is set up to work well for npm, with a reasonable configuration.

* ts is set up
* menu-driven selection and updates of what type of interfaces, constants and functions you want to expose.
* option for groupings of constants and/or functions
* testing set up with ava, with nyc coverage
* linting with eslint
* set up to work with Travis CI and semantic-release. A `pre-commit` ghook includes testing and coverage thresholds

And, we can handle the upgrades for all the packages that you don't add yourself.  This package uses **[geenee](https://www.npmjs.com/package/geenee)**. So, you can regenerate your code without losing your changes whenever `packrat` updates!

# <a name="wrench-how"></a>:wrench: How
Follow the steps below.  
## (1) Create a Starter CLI
Define `$CODE_DIR` as the path to your desired directory for your package. Then run
```
npx packrat $CODE_DIR
```
and answer the interactive questions.

## (2) Update the Commands
Call 
```
npx geenee settings $CODE_DIR
```
and follow the prompts.

The `general` option is there if you want to change any of the interactive answers you gave in step 1.  The `static` option is what you need to choose now.  You can add one of two things:
1. __typeCategory__: a grouping for types of interfaces that you'll want to expose.  That's useful if you will want your package users to have access to your defined types.
2. __grouping__: a grouping for constants and/or functions that you want to expose.  
For each type of category or grouping, you can then add as many as you'd like.  If you give descriptions, it will all show up in your generated README file.

You will be prompted to regenerate your code after you make changes.  You can also call that separately:
```
npx geenee generate $CODE_DIR
```

## (3) Change the Custom Code
Of course, you still have to create your code.  You should be able to do just about anything possible in Node using Typescript.  But, follow the [safe custom code practices of geenee](https://geenee.nostack.net/Safe-Custom-Code) to be able to reapply this template in the future without losing anything.

For every grouping, you will see a generated file in `src/groupings`.  You can just define things there, but best is to create things in `src/custom` and then include them in the `helpers` section or require them directly.

### Using Continuous Integration
You need to:
1. follow the directions to set up your package with Travis to be configured to GitHub

2. follow the instructions at `semantic-release` to get the `GH_TOKEN` and the `NPM_TOKEN`, and insert them into your repository settings at Travis. 

## (4) Updating Your Template
Take a minute and set up alerts about releases to this template.
1. Go to the [GitHub repo](https://github.com/YizYah/ts-packrat) and click the arrow by the `Watch` button on the upper right.

![watch](images/watch.jpg)

2. Choose "Custom", and then select "Releases".

![releases](images/custom-releases.jpg)

Before you update your template, check your code for safety by calling:
    ``` 
    npx geenee check $CODE_DIR
    ```
To reapply the template with a newly released version, just the first command again.  Make sure to use the same path for the legacy `$CODE_DIR`.
```
npx geenee settings $CODE_DIR
```
All of the settings and custom changes in the `$CODE_DIR` cli will be retained if you followed the [safe custom code practices of geenee](https://geenee.nostack.net/Safe-Custom-Code).

## Replacing the Template
One drawback of templates, even updatable ones, is that sometimes you will want to do something that the template doesn't support.  For instance, maybe you'd rather use a Circle CI rather than Travis.

One bad option is to start making changes that will be removed if you try to update the template.  A much better option is to fork from ts-packrat and create your own version, and then update your code using your own new template.

Then, consider releasing it on NPM and letting us know!  Because the whole idea behind the geenee project is that templates are not just *updatable*, but also *exchangeable*!  You could even call it something like `ts-packrat-circle`!  The more that people make available, the more options for other users of ts-packrat.


# <a name="heavy_exclamation_mark-help"></a>:heavy_exclamation_mark: Help
We've started a [wiki](https://github.com/YizYah/ts-packrat/wiki), intended for someone new to npm and node.

Post on [geenee discussions](https://github.com/YizYah/geenee/discussions/).
# <a name="eyes-see-also"></a>:eyes: See Also
[geenee documentation](https://geenee.nostack.net/)
