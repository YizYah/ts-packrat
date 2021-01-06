
![easy](images/packrat.jpg)

Instant typescript npm packages.

[Warning: still beta.]

# Why
So you don't have to worry about anything but writing your TS code.  This package uses [ns-flip](https://www.npmjs.com/package/ns-flip), so you can regenerate your code without losing your changes whenever `packrat` updates!

# How
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
npx ns-flip settings $CODE_DIR
```
and follow the prompts.

You will be prompted to regenerate your code after you make changes.  You can also call that separately:
```
npx ns-flip generate $CODE_DIR
```

## (3) Change the Custom Code
Of course, you still have to create your code.  You should be able to do just about anything possible in Node using Typescript.  But, follow the [safe custom code practices of ns-flip](https://ns-flip.nostack.net/Safe-Custom-Code) to be able to reapply this template in the future without losing anything.

## (4) Updating Your Template
Take a minute and set up alerts about releases to this template.
1. Go to the [GitHub repo](https://github.com/YizYah/ts-packrat Explore
@YizYah
Learn Git and GitHub without any code!

Using the Hello World guide, you’ll start a branch, write comments, and open a pull request. ) and click the arrow by the `Watch` button on the upper right.

<img src="images/2.jpg" alt="Watch Button" title="Watch" width="200">

2. Choose "Custom", and then select "Releases".

<img src="images/3.jpg" alt="Watch Releases" title="Releases" width="200">

Before you update your template, make sure to check your code for safety by calling:
    ``` 
    npx ns-flip check $CODE_DIR
    ```
To reapply the template with a newly released version, just the first command again.  Make sure to use he same path for the legacy `$CODE_DIR`.
```
npx ns-flip settings $CODE_DIR
```
All of the settings and custom changes in the `$CODE_DIR` cli will be retained if you followed the [safe custom code practices of ns-flip](https://ns-flip.nostack.net/Safe-Custom-Code).

# Help
Post on the [ns-flip Community](https://spectrum.chat/ns-flip?tab=posts).

# See Also
[ns-flip documentation](https://ns-flip.nostack.net/Home)
