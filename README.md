#ANGULAR+ TAILWINDCSS
-------------------------------------------------------------------
ng new ATL
cd ATL

//what the options i used
? Would you like to add Angular routing? Yes
? Which stylesheet format would you like to use?
> SCSS

code . 
// :) I know you use it
#let's begin the magic
-------------------------------------------------------------------

npm i tailwindcss autoprefixer postcss postcss-import postcss-loader postcss-scss -D
ng add ngx-build-plus

npx tailwind init --full -p

//tailwind.config.js 
//files which can overwrite/modify css utilities

 purge: {
    enabled: false,// true, Enable it in production
    content: ['./src/**/*.html', './src/**/*.ts', './src/**/**/*.html', './src/**/**/*.ts'],
  },

//postcss.config.css


create a file webpack.config.js
//webpack.config.js


module.exports = {
    module: {
      rules: [
        {
          test: /\.scss$/,
          loader: 'postcss-loader',
          options: {
              postcssOptions:{
                ident: 'postcss',
                syntax: 'postcss-scss',
                plugins: () => [
                  require('postcss-import'),
                  require('tailwindcss'),
                  require('autoprefixer'),
                ]
            }
          }
        }
      ]
    }
  };

#Edit angular.json in below sections
-------------------------------------------------------------------
Build
Serve
Test

"build": {
          "builder": "ngx-plus bla bla",
          "options": {  
          "extraWebpackConfig": "webpack.config.js",  
	----

"serve": {
          "builder": "ngx-plus bla bla",
          "options": {
            "extraWebpackConfig": "webpack.config.js",  
	----

"test":{
          "builder": "ngx-plus bla bla",
          "options": {
            "extraWebpackConfig": "webpack.config.js",  
	----

#STYLE.CSS
-------------------------------------------------------------------
@import "tailwindcss/base";
@import "tailwindcss/components";
@import "tailwindcss/utilities";
