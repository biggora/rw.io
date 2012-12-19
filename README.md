## About

Socket.IO bindings for [CompoundJS](http://compoundjs.com/)

## Installataion

    $compound install https://github.com/1602/rw.io.git

or manual

    $npm install socket.io rw.io
    $echo "require('rw.io');" >> npmfile.js

## API

### routes

    map.socket('some-event', 'controller#action');

When client emit event `some-event`, then `action` action of controller
`controller` will gain control. Data passed to event will be available as
`params` variable.

### controller

    action('some-action', function () {
        socket().emit('event', {some: 'data'}); // send 'event' to current client
        socket(anotherSessionID).emit('hello'); // send 'hello' to another user
                                                // identifyed by anotherSessionID
    });

Any controller action (both socket and non-socket) can emit some event with
connected client (current session client). If you want to communicate with
another user need to specify session id as param of `socket` method.

Other socket.io API will be available later: join, broadcast, etc..

## MIT License

```
Copyright (C) 2012 by Anatoliy Chakkaev

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```
