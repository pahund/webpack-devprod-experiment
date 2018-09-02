# webpack-devprod-experiment

With [webpack](https://webpack.js.org) 4, you can set `mode: 'production'` in your webpack config.

In your code, check for development mode like this:

if (process.env.NODE_ENV === 'development') {
    /* development only */
    alert('hiya!');
}

When webpack creates a bundle with mode: 'production', all the code inside these if clauses, along with the if clauses themselves, will be automatically removed from the bundle.

There is no need to use the [define](https://webpack.js.org/plugins/define-plugin/) plugin explicitly (it is used by webpack “under the hood”), and it's not necessary to use something like [webpack-unassert-loader](https://www.npmjs.com/package/webpack-unassert-loader) or [webpack-strip-block](https://www.npmjs.com/package/webpack-strip-block).

I've made this repo to demonstrate. After checking out the code and installing dependencies with `npm install`, you can run either of these commands:

* `npm run build-dev`
* `npm run build-prod`

…to have webpack create a [bundle-dev.js](bundle-dev.js) and a [bundle-prod.js](bundle-prod.js) file, respectively.

If you take a look at those bundles, you'll see that the log statement `********** PRODUCTION **********` is only included in the production bundle, and the log statement `********** DEVELOPMENT **********` only in the development bundle.

See related question on Stack Overflow: https://stackoverflow.com/questions/45776264/remove-some-code-lines-in-production-distribution-files
