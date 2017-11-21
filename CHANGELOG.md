# Change Log

All notable changes to this project will be documented in this file.
See [Conventional Commits](https://conventionalcommits.org) for commit guidelines.

  <a name="0.2.3"></a>
## [0.2.3](https://github.com/jdiaz5513/capnp-ts/compare/v0.2.2...v0.2.3) (2017-11-21)


### Bug Fixes

* **compiler:** relax compiler settings for capnpc-js ([#84](https://github.com/jdiaz5513/capnp-ts/issues/84)) ([5e89626](https://github.com/jdiaz5513/capnp-ts/commit/5e89626)), closes [#83](https://github.com/jdiaz5513/capnp-ts/issues/83)




  <a name="0.2.2"></a>
## [0.2.2](https://github.com/jdiaz5513/capnp-ts/compare/v0.2.1...v0.2.2) (2017-11-20)


### Bug Fixes

* **build:** update lerna configuration ([51024e5](https://github.com/jdiaz5513/capnp-ts/commit/51024e5))
* **compiler:** do not generate imports for external files ([#82](https://github.com/jdiaz5513/capnp-ts/issues/82)) ([b1dd5b3](https://github.com/jdiaz5513/capnp-ts/commit/b1dd5b3))




# 0.2.1

Structs can be imported from other schema files.

```capnp
@0xfc552bdafbb0b889;

using Bar = import "import-bar.capnp";

struct Foo {
baz @0 :Bar.Baz;
}
```

# 0.2.0

The message factory functions have been integrated into a revamped message constructor.

```typescript
capnp.Message.fromArrayBuffer(buf);       // 0.1.6
new capnp.Message(buf, false);            // >=0.2.0

capnp.Message.fromPackedArrayBuffer(buf); // 0.1.6
new capnp.Message(buf);                   // >=0.2.0

capnp.Message.fromBuffer(buf);            // 0.1.6
new capnp.Message(buf, false);            // >=0.2.0

capnp.Message.fromPackedBuffer(buf);      // 0.1.6
new capnp.Message(buf);                   // >=0.2.0

capnp.Message.fromSegmentBuffer(buf);     // 0.1.6
new capnp.Message(buf, false, true);      // >=0.2.0
```

Many other methods that were intended to be private are also no longer exposed on their classes, and private members have been moved to `_capnp` properties on all Pointer types.

Don't touch anything inside `_capnp`!
