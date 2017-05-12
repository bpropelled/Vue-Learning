# Vue JS NOTES 
this is the file for keeping tracks of the notes for learning vue from Lynda

## Installing VUE
- Installing Vue is easy and invloves downloading the files from the vue website or using the CdN script tags in the file
```html
<script src="https://unpkg.com/vue"></script>
```
- This will install the latest version of vue

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
  data: {
        message: "This is a sample message"
  }
});
```
