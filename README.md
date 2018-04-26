ejsc
====

## Usage

`ejsc <file> [output] [data]`


## Examples

`ejsc myPage.html.ejs` - Compiles *myPage.html.ejs* to *myPage.html*.

`ejsc template.ejs compiled.html` - Compiles *template.ejs* to *compiled.html*.

`ejsc myPage.ejs myPage.html "{ \"value\": 123 }"` - Compiles *myPage.ejs* passing the specified object as global context.


## Complete Example

`ejsc file1.txt.ejs output.txt "{ \"something\": \"from arguments\" }"`

### file1.txt.ejs
```
Hello, World!

This is <%- filename %>, something = <%- something %>

<%- compile('file2.txt.ejs', { something: "test" }) %>
```

### file2.txt.ejs
```
This is <%- filename %>, something = <%- something %>
```

### output.txt
```
Hello, World!

This is file1.txt.ejs, something = from arguments

This is file2.txt.ejs, something = test
```


## License

Copyright © 2018 Fabio Iotti. ejsc is released under the terms of the MIT License.
