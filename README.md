# MetaPost - a language grammar for [highlight.js](https://highlightjs.org/)


MetaPost refers to both a programming language and the interpreter of the
MetaPost programming language. Both are derived from Donald Knuth's Metafont
language and interpreter. MetaPost produces vector graphic diagrams from a
geometric/algebraic description. The language shares Metafont's declarative
syntax for manipulating lines, curves, points and geometric transformations. 

## Usage

Simply include the Highlight.js library in your webpage or Node app, then load this module.

### Static website or simple usage

Simply load the module after loading Highlight.js. You'll use the minified version found in the `dist` directory. This module is just a CDN build of the language, so it will register itself as the Javascript is loaded.

```html
<script type="text/javascript" src="/path/to/highlight.min.js"></script>
<script type="text/javascript" charset="UTF-8"
  src="/path/to/highlightjs-metapost/dist/metapost.min.js"></script>
<script type="text/javascript">
  hljs.highlightAll();
</script>
```

### Using directly from the UNPKG CDN

```html
<script type="text/javascript"
  src="https://unpkg.com/highlightjs-cypher/dist/metapost.min.js"></script>
```

- More info: <https://unpkg.com>

### With Node or another build system

If you're using Node / Webpack / Rollup / Browserify, etc, simply require the language module, then register it with Highlight.js.

```javascript
var hljs = require('highlightjs');
var hljsMetapost = require('highlightjs-metapost');

hljs.registerLanguage("metapost", hljsMetapost);
hljs.highlightAll();
```

### React

You need to import both Highlight.js and third-party language like Metapost:

```js
import React, {Component} from 'react'
import 'highlight.js/scss/darcula.scss' # your favourite theme
import metapost from './metapost'
import hljs from 'highlight.js'
hljs.registerLanguage('metapost', metapost);

class Highlighter extends Component
{
  constructor(props)
  {
    super(props);
    hljs.highlightAll();
  }

  render()
  {
    let {children} = this.props;
    return
    {
      <pre ref={(node) => this.node = node}>
        <code className="metapost">
          {children}
        </code>
      </pre>
    }
  }
}

export default Highlighter;
```

## License

Highlight.js is released under the CC0 1.0 License. 

### Author

Maxime Chupin <chupin@ceremade.dauphine.fr>

## Links

- The official site for the Highlight.js library is <https://highlightjs.org/>.
- The Highlight.js GitHub project: <https://github.com/highlightjs/highlight.js>
