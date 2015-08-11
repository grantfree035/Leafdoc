
# Leafdoc


Leafdoc (or 🍂📄 for short) is custom NaturalDocs-like documentation parser to produce Leaflet-style documentation.

Very much a WIP right now.

The goal is to produce documentation that looks exactly the same as the LeafletJS current one.

Markdown is supported for long comments and example blocks.


## Try


See [Leafdoc's documentation as generated by Leafdoc](http://ivansanchez.github.io/Leafdoc/doc.html).


### Try it yourself

```
git clone [...]
npm install
js test.js > leafdoc.html
```


## Write

The syntax is pretty much the tried-and-true directives-in-comment-blocks from JSdoc, NaturalDocs and a gazilion others. But instead of an `@` symbol, Leafdoc uses a leaf:

```
/*
 * 🍂method addDir
 * 🍂param dirname, String
 * 🍂param extension, String
 * 🍂returns this
 *
 * Recursively scans a directory, and parses any files that match the given `extension`
 */
```


### Valid directives

* `🍂class` and `🍂namespace` should be at the top of your files. They define the context of the rest of the directives. A namespace can be used in more than one file (for example, when plugging more functionality to an existing class).
* `🍂example` lets some space to demonstrate how the class / namespace is meant to be used.
* `🍂section` allows you to group several functions, events, methods or options together, thematically.
* `🍂method` and `🍂function` are pretty much the same (one for instances, other for static funcs). Both can have zero or more `🍂param`s and one `🍂returns`.
* I will implement `🍂event` and `🍂option` eventually.
* Anything can have several `🍂comment`s, exmplaining the thing. The `🍂comment` directive can be ommited, because any line without an explicit directive equals to one (but only for comment blocks that already have a 🍂 directive - non-🍂 blocks are ignored).



### Customization

At some point in the future it shall be easy to use a different set of `handlebars` templates.


## Troubleshooting

### I'm using Debian and I cannot see the leaf character!

Run `apt-get install ttf-ancient-fonts` and don't ask why the fallback file for emojis is packaged as "ancient fonts".

