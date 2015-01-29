---
title: Configuration
layout: en
permalink: /user/configuration/
---

Linthub can be configured which analyzers to use. Each analyzer can be configured individually.

<div id="toc"></div>

## Platform

```
platform: linux # | osx
```

## Build

```
build:
- make clean
- make
```

## Test
```
test:
- ./hello
```

## Analyzers

```
analyzers:
```

### C++
#### Cpplint
```
 - cpplint: true
   include: ["*.cpp", "*.h", "*.hpp", "*.c"]
   path: ./src/
   filters:
   - -whitespace
   - +whitespace/braces
   style: google # webkit | google
```

### Go
#### Golint
```
 - golint: true
   path: ./transfersh-server/
   min_confidence: 0.8
```

#### Govet

```
 - govet: true
   path: ./transfersh-server/
```

### Javascript
#### JSLint
```
 - jslint: true
   params:
   - evil
```
#### ESLint
```
 - eshint: true
   params: test2
```
### JSHint
```
 - jshint: true
```

### Coffeescript

#### Coffeelint
```
 - coffeelint: true
```

### Dart

#### Dartanalyzer

```
 - dartanalyzer: true
```

### ReactJS

#### JSXHint
```
 - jsxhint: true
````

### Scala
```
 - scalastyle: true
```

### Ruby
```
 - rubocop: true
   targets: ["."]
```

### CSS

#### Csslint
```
 - csslint: true
   errors:
   warnings:
   ignore:
   exclude-list:
```

### PHP
#### PHPCS
```
 - phpcs: true
```

### Shell
#### Shellcheck
```
 - shellcheck: true
   interpreter: zsh
```

### Ojbective-C

#### OCStyle
```
 - ocstyle: true
   patterns: ["*.cpp", "*.h", "*.hpp", "*.c"]
   allowed: ["*.cpp", "*.h", "*.hpp", "*.c", "*.m"]
   include: ["*.cpp", "*.h", "*.hpp", "*.c"]
```

### CMake
#### Polysquare CMake
```
 - polysquare-cmake: true
   allowed: ["CMakeLists.txt"]
```

### Python
#### Flake8
Flake8 is a wrapper around these tools:

 - PyFlakes
 - pep8
 - Ned Batchelder’s McCabe script

Reference: [flake8](http://flake8.readthedocs.org/en/2.3.0/)

```
 - flake8: true
```

### Java
#### PMD
```
 - pmd: true
```
#### Checkstyle
```
 - checkstyle: true
   style: google # | sun
```

### Markdown
#### Markdownlint
```
 - markdownlint: true
```
