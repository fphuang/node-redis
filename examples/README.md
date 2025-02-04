# Node Redis: Examples

This folder contains example scripts showing how to use Node Redis in different scenarios.

| File Name                | Description                          |
|--------------------------|--------------------------------------|
| `connect-as-acl-user.js` | Connect to Redis 6 using an ACL user |

## Contributing

We'd love to see more examples here. If you have an idea that you'd like to see included here, submit a Pull Request and we'll be sure to review it!  Don't forget to check out our [contributing guide](../CONTRIBUTING.md).

### Coding Guidelines for Examples

When adding a new example, please follow these guidelines:

* Add your code in a single JavaScript file per example, directly in the `examples` folder
* Do not introduce other dependencies in your example
* Give your `.js` file a meaningful name using `-` separators e.g. `adding-to-a-stream.js`
* Indent your code using 2 spaces
* Use the single line `//` comment style and comment your code
* Add a comment at the top of your `.js` file describing what your example does
* Add a comment at the top of your `.js` file describing any Redis commands that need to be run to set up data for your example (try and keep this minimal)
* Use semicolons
* Use `async` and `await`
* Use single quotes, `'hello'` not `"hello"`
* Place your example code in a single `async` function where possible, named according to the file name e.g. `add-to-stream.js` would contain `const addtoStream = async () => { ... };`, and call this function at the end of the file e.g. `addToStream();`
* Unless your example requires a connection string, assume Redis is on the default localhost port 6379 with no password
* Use meaningful example data, let's not use `foo`, `bar`, `baz` etc!
* Leave on empty line at the end of your `.js` file
* Update this `README.md` file to add your example to the table

Use [connect-as-acl-user.js](connect-as-acl-user.js) as a guide to develop a well formatted example script.

### Example Template

Here's a starter template for adding a new example, imagine this is stored in `do-something.js`:

```javascript
// This comment should describe what the example does
// and can extend to multiple lines.

// Set up the data in redis-cli using these commands:
//   <add your command(s) here, one per line>

import { createClient } from 'redis';

async function doSomething() {
  const client = createClient();

  await client.connect();

  // Add your example code here...

  await client.quit();
}

doSomething();
```
