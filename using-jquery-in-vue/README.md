# using-jquery-in-vue

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```

For detailed explanation on how things work, consult the [docs for vue-loader](http://vuejs.github.io/vue-loader).

## Work contents
#### 1. vue init
```
vue init webpack-simple
```
#### 2. npm install
```
npm install
```
#### 3. npm install jquery
```
npm install jquery --save
```
#### 4. main.js
```javascript
import $ from 'jquery'
window.$ = $;
```
#### 4. webpack.config.js
```javascript
if (process.env.NODE_ENV === 'production') {
  module.exports.devtool = '#source-map'
  // http://vue-loader.vuejs.org/en/workflow/production.html
  module.exports.plugins = (module.exports.plugins || []).concat([
      // ...
      new webpack.ProvidePlugin({
        $: 'jquery',
        jquery: 'jquery',
        'window.jQuery': 'jquery',
        jQuery: 'jquery'
      }) 
      // ...
  ])
}
```

## Precautions
- jquery selector로 HTML 태그를 접근할 수 있는 시점은 mounted 훅이다. 