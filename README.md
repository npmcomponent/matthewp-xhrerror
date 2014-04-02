*This repository is a mirror of the [component](http://component.io) module [matthewp/xhrerror](http://github.com/matthewp/xhrerror). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/matthewp-xhrerror`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# XhrError

A generic Error object for use when performing XHR requests. XHR component writers are encouraged to use this Error object to signal errors / incomplete requests.

## Installation

**XhrError** is a [component](https://github.com/component/component).

    $ component install matthewp/xhrerror

## Usage

XhrError is a tiny object that serves 1 purpose, to signal an error in an XHR requests.

```javascript
var XhrError = require('xhrerror');

function doAjaxyRequest(url, callback) {

  ...
  // Oops, there was an error.
  var err = new XhrError("Oops, couldn't find that.", 404);
  callback(err);
}
```

## API

### XhrError(message, status, request)

Create a new ``XhrError``. Optionally provide a ``message`` string, a ``status`` code and the full failed ``request``.

### XhrError#status

The status code returned from the XHR attempt.

### XhrError#message

Inheriting from ``Error#message``, the string message for the error.

### XhrError#request

Inheriting from ``Error#request``, the request obj for the error. Access err.req.getAllResponseHeaders().

### XhrError#stack

Inheriting from ``Error#stack``, the stack trace from which the XhrError was created.

## Dependencies

None.