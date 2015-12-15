RecXML to JSON
based on script from https://github.com/buglabs/node-xml2json

```javascript
var parser = require('../recxmljsonparser');
var promise = require('promise');
var fs = require('fs');
var util = require('util');


var pReadFile  = promise.denodeify(fs.readFile);

pReadFile('./data_example/exemple_1.xml', 'utf8')
.then(function  (recxml_data,err) 
{

  var jsonString = parser.toJson(recxml_data); //returns a string containing the JSON structure by default 
  console.log(jsonString);

}
,function  (err) {
  console.log(err);
});
```

## License
(The MIT License)

Copyright 2015 BugLabs. All rights reserved.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to
deal in the Software without restriction, including without limitation the
rights to use, copy, modify, merge, publish, distribute, sublicense, and/or
sell copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS
IN THE SOFTWARE.
