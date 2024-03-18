Major version bump due to change in return value.

### Version 2.0:
**XML Tagnames are no more converted from dashes to underscore automatically.**

To get the old behaviour back, use this snippet:

```js
const router = new netconf.Client({
    // ...
});

function convertNames(name) {
    return name.replace(/-|:/g, '_');
}

router.parseOpts.tagNameProcessors = [ convertNames ];
router.parseOpts.attrNameProcessors = [ convertNames ];
```

