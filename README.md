# npm-dts

_by Vytenis Urbonavičius_

This utility generates single index.d.ts file for whole NPM package.

It allows creating NPM library packages without TypeScript sources and yet still keeping code suggestions wherever these libraries are imported.

# Installation

```
npm install -g npm-dts
```

# Usage

**To see full _CLI_ help, run without arguments:**

```
npm-dts
```

**Typical usage:**

```
cd /your/project
npm-dts -r . generate
```

Please make sure that target project has "typescript" installed (in _node_modules_).

**Integration into package.json:**

```
{
  ......
  "scripts": {
    "prepublishOnly": "npm run dts && ......",
    "dts": "./node_modules/.bin/npm-dts -r . generate"
  }
  ......
}
```

**Additional supported configuration:**

- **-e** - change main src file from index.ts to something else
- **-r** - root of your project containing project.json
- **-t** - set tmp directory - used for storing some files during generation. Note that tool completely deletes this folder once finished.
- **-c** - pass additional directives to _TSC_. Note that they are not validated or checked for suitability.

# Contribution

Contribution is welcome in a form of pull requests and issues.
