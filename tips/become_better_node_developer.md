1. Use [JavaScript Standard Style](https://github.com/standard/standard) and/or [eslint-plugin-standard](https://github.com/xjamundx/eslint-plugin-standard) in your project.
2. Monitor your applications using Elasticsearch, Kibana, Logstash, CollectD, etc.
3. Use build systems like Gulp, Grunt and Webpack.
4. Update dependencies on weekly basis. Use [ncu](https://www.npmjs.com/package/npm-check-updates)
5. Pick the right DB - MongoDB doesnt have to be the Defacto just because it works to great with nodejs. Use [knex](http://knexjs.org/) if using SQL.
6. Use semantic versioning (3 digits - major version, minor version, patch).
Major version change: API change is not backward compatible.
Minor version change: Few new features added, but API change is backward compatible.
Patch version change: Bug fixes.

# The 12 factor application in building web apps
- One codebase tracked in revision control
- Explicitly declare and isolate dependencies
- Store config in the environment
- Treat backing services as attached resources
- Strictly separate build and run stages
- Execute the app as one or more stateless processes
- Export services via port binding
- Scale out via the process model
- Maximize robustness with fast startup and graceful shutdown
- Keep development, staging, and production as similar as possible
- Treat logs as event streams
- Run admin/management tasks as one-off processes
Read more about each [here](https://12factor.net/codebase)

7. Get acquainted with import and import() - They are natively supported since version 8.5 behind the --experimental-modules flag
8. Get familiar with HTTP/2 - Available since v8.8 without a flag. It has server push and multiplexing, which paves way for efficient native module loading in browsers.
9. mark and measure - Node v8.5. To measure event loop duration.
```
const { performance } = require('perf_hooks')
performance.mark('A')
setTimeout(() => {
  performance.mark('B')
  performance.measure('A to B', 'A', 'B')
  const entry = performance.getEntriesByName('A to B', 'measure')
  console.log(entry.duration)
}, 10000)
```