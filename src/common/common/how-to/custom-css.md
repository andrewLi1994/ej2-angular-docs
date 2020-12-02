# How to use Custom CSS file in Angular Application

This section explains about how to use the custom styles generated by [Theme Editor](https://ej2.syncfusion.com/themestudio/?theme=material) to an Essential JS2 Angular components.

## Create an Angular Application

Create an angular application with Essential JS 2 Angular Components using [documentation](https://ej2.syncfusion.com/angular/documentation/introduction/).

## Generating Custom CSS file

Generate custom CSS file using [theme-studio](https://ej2.syncfusion.com/themestudio/?theme=material).

## Adding Custom CSS in Angular application

Add the generated Custom CSS file in your created Angular application inside `./src/`.

## Custom style mapping

Add Custom CSS file path in `./angular.json` file under `architect/build/options/styles` property like below

```typescript
"styles": [
             "src/styles.css",
             "src/custom-material.css"
          ],
```

## Run Angular Application

Then Run your Angular application and you will get Essential JS 2 Angular Components with custom styles.