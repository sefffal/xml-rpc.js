# xml-rpc.js
Library for XML-RPC from JavaScript across domains.

Based on the Mimic JS library oringinally written by Carlos Eduardo Goncalves; see below for license.

Provides an easy to use object-oriented interface for XML-RPC.
Transparently converts objects to JS literals were practical (e.g. String('abc') -> 'abc').
Allows using XML-RPC with servers on different domains and/or ports than the originating web server.

## Limitations
At this stage, the library relies on syncronous AJAX calls to allow completely transparent method invocation.
In the future, there will be an option to return a JS Promise object instead of the result, and use asyncronous AJAX instead.

## Examples

### Initializing a connection
~~~~
var rpc = new XmlRpcConnection({
    url:     "http://<some_url>",    // URL to XML-RPC service
    log:     true,                   // If true, logs all requests to console
    record:  false                   // If true, records all requests and results to rpc._requests
});
~~~~
All options are optional aside from the url.

### Invoking a remote method.
~~~
rpc.method_name('param1', 'param2', 'etc');
~~~
All the error handling is taken care of but if you like you can catch{} it. In addition, methods that fail return undefined.







## Original License

Mimic (XML-RPC Client for JavaScript) v2.0.1
Copyright (C) 2005-2009 Carlos Eduardo Goncalves (cadu.goncalves@gmail.com)

Mimic is dual licensed under the MIT (http://opensource.org/licenses/mit-license.php) 
and GPLv3 (http://opensource.org/licenses/gpl-3.0.html) licenses.
