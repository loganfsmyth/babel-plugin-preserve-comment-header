# babel-plugin-preserve-comment-header

Explicitly ensure that the first comment at the top of the processed file,
if it matches the given pattern, _stays_ at the top of the file.

Often Babel will insert `use strict` or any number of other things at the
top of a file. While often the top comment will just be documentation attached
to the first function, and thus _should_ be pushed down, sometimes these
comments are things like license headers, which should be left at the top.

## Usage

```
{
  "plugins": [
    "babel-plugin-preserve-comment-header"
  ]
}
```

which will by default preserve any comments containing the test `@license`.

### Custom pattern

```
{
  "plugins": [
    ["babel-plugin-preserve-comment-header", { pattern: "customString" }]
  ]
}
```

or if you are in a non-JSON config, a RegExp is also permitted:

```
{
  "plugins": [
    ["babel-plugin-preserve-comment-header", { pattern: /customString/ }]
  ]
}
```
