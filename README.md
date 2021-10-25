# Less error on `vite dev`

[UIkit less docs](https://getuikit.com/docs/less)



```
[plugin:vite:css] Error evaluating function `round`: argument must be a number
/home/sergey/project/node_modules/uikit/src/less/components/table.less:264:77
262|      .uk-table-responsive th:not(:first-child):not(.uk-table-link),
263|      .uk-table-responsive td:not(:first-child):not(.uk-table-link),
264|      .uk-table-responsive .uk-table-link:not(:first-child) > a { padding-top: round(@table-cell-padding-vertical / 3) !important; }
   |                                                                               ^
265|  
266|      .uk-table-responsive th:not(:last-child):not(.uk-table-link),
    at less (/home/sergey/project/node_modules/vite/dist/node/chunks/dep-9f74b403.js:34496:33)
    at async compileCSS (/home/sergey/project/node_modules/vite/dist/node/chunks/dep-9f74b403.js:34127:34)
    at async TransformContext.transform (/home/sergey/project/node_modules/vite/dist/node/chunks/dep-9f74b403.js:33776:50)
    at async Object.transform (/home/sergey/project/node_modules/vite/dist/node/chunks/dep-9f74b403.js:50353:30)
    at async transformRequest (/home/sergey/project/node_modules/vite/dist/node/chunks/dep-9f74b403.js:65248:29)
    at async viteTransformMiddleware (/home/sergey/project/node_modules/vite/dist/node/chunks/dep-9f74b403.js:65376:32

```

## Update October 2021

This less error can be solved with additional less configuration:

We need vite.config.js file for it:

```
export default {
  css: {
    preprocessorOptions: {
      less: {
         math: 'always'
      }
    }
  }
}
```