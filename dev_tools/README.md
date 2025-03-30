# Using Chrome DevTools

Chrome DevTools is a powerful set of developer tools built into Google Chrome that helps in debugging, performance analysis, and optimizing web applications.

## 1 - Opening DevTools
### Methods to Open DevTools:
- **Right-click on an element** → Select `Inspect`
- Press `F12` or `Ctrl + Shift + I` (Windows/Linux)
- Press `Cmd + Option + I` (Mac)

## 2 - Elements Panel
Allows inspection and modification of the DOM and CSS.
- Edit HTML elements
- Modify CSS styles live
- View and debug event listeners

### Example:
```html
<div id="example">Hello World</div>
```
- Right-click `div` → Inspect → Modify text directly

## 3 - Console Panel
Used to run JavaScript commands and view logs.
```js
console.log("Hello DevTools");
```
- View errors, warnings, and logs
- Use `console.table(data)` to display structured data

## 4 - Sources Panel
- Debug JavaScript by setting breakpoints
- Step through code execution
- View and edit source files

### Example: Setting a Breakpoint
```js
function greet() {
  console.log("Hello"); // Set breakpoint here
}
greet();
```

## 5 - Network Panel
Monitors network requests, responses, and performance.
- View API requests (`XHR` & `Fetch`)
- Inspect request/response headers
- Analyze loading speed

### Example: Monitor an API Request
1. Open `Network` tab
2. Reload page
3. Click a request to inspect details

## 6 - Performance Panel
- Analyze page load time
- Identify slow scripts and bottlenecks

## 7 - Memory Panel
- Detect memory leaks
- Analyze heap snapshots

## 8 - Application Panel
- Manage cookies, local storage, and session storage
- Inspect IndexedDB and Web SQL

## 9 - Security Panel
- Check SSL/TLS status
- Identify mixed content issues

## 10 - Lighthouse Panel
- Run performance and SEO audits
- Get improvement suggestions

## Summary
| Panel | Purpose |
|-------|---------|
| Elements | Modify HTML & CSS |
| Console | Run JavaScript & debug logs |
| Sources | Debug JavaScript & set breakpoints |
| Network | Monitor network requests |
| Performance | Analyze speed & efficiency |
| Memory | Detect memory issues |
| Application | Manage storage & databases |
| Security | Check SSL & vulnerabilities |
| Lighthouse | Audit performance & SEO |

Chrome DevTools is an essential tool for frontend and backend debugging, helping developers optimize web applications efficiently.

