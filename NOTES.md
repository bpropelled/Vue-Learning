# Vue JS NOTES 
this is the file for keeping tracks of the notes for learning vue from Lynda

## Installing VUE
- Installing Vue is easy and invloves downloading the files from the vue website or using the CdN script tags in the file
```html
<script src="https://unpkg.com/vue"></script>
```
- This will install the latest version of vue
>**If you declre the Vue file at the top of the document you will not get the side effect of showing the string interpolation when the page loads.  When you throw this file at the end of the document like normal js files, you will get a brief flashing of raw elements before Vue updates the dom**

## Using it in a project
- The simplest form of adding vue to a project would involve
1. Add the script tag
2. Declare a Vue element and add some string interpolation of the data element (message is in the data object)
```html
<div id="app">{{ message }}</div>
```
3. Instantiate the Vue object
```js
new Vue ({
  //1 add an element to the vue object
  el: '#app',
  //Add some data
  data: {
        message: "This is a sample message"
  }
});
```
>**Note: If the double curly braces are not your thing, then you can create your own custom DELIMITERS.  For more info on Vue Delimiters, visit  https://vuejs.org/v2/api/#delimiters**

>**Note : Vue is interpreted from Top to Bottom so make sure that the html element is declared BEFORE the Vue instance is created.**

## Data Binding in Vue
> Data binding is the process that establishes a connection between the application UI and business logic. If the binding has the correct settings and the data provides the proper notifications, then, when the data changes its value, the elements that are bound to the data reflect changes automatically.

#### What is "String Interpolation"
>String interpolation is used to bind data to an element dynamically like show above using the template tags **{{ message }}**

A good exmaple of using this is to dynamically add a SRC tag to an element
```html
<a id="app" href="{{ url }}"></a>
```
```javascript
new Vue ({
    el: '#app',
    data: {
        url: 'https://www.google.ca'
    }
});
```

>**NOTE: When using data binding inside attribute tags like ID, CLASS or HREF, you will need to use "v-bind" or the colon shorthand like this**
```html
  <!-- NOT ALLOWED FOR ATTR  -->
                    <a href=" {{ url }}" class="btn btn-lg btn-primary">Go to Google</a>
                    <!-- Using Vue tags as an elements attribute - use v-bind or the colon shorthand like below -->
                   <a v-bind:href=" url " class="btn btn-lg btn-primary">Go to Google</a>
                    <!-- OR  -->
                   <a :href=" url " class="btn btn-lg btn-primary">Go to Google</a>
                   <!-- OR you can mess it with like so by appending to the attr like using normal js  -->
                   <a :href=" url + '?test=testies' " class="btn btn-lg btn-primary">Go to Google</a>
```
