# vue-list-grid

> Vue.js List + Grid Component

Allows you to switch between list and grid view of the given data. You can use any `list` and `grid` controls of your choice to render the actual views.

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

# run unit tests
npm run unit

# run e2e tests
npm run e2e

# run all tests
npm test
```

## Usage

````
<listGrid view='list' 
          :data=listGridData 
          :listRenderer=listRenderer 
          :gridRenderer=gridRenderer 
          caption="The Caption">
</listGrid>
````