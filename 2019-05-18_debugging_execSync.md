# Debugging execSync in Node.js

### 5/18/2019

Node.js has a handy tool for executing commands, called 'execSync'. Should you encounter an execption, you may need to raise a custom error or debug the error that was raised by an exeception. To do this you can use `try { ... } catch(e) { ... }`

```javascript
try {
  execSync('some_arbitrary_command')
} catch(e) {
  // does some custom stuff with e
}
```

Tags: Node, javascript, general
