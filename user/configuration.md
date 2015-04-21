---
title: Configuration
layout: en
permalink: /user/configuration/
---

Linthub reads its configuration from the .linthub.yml file. .linthub.yml has a list of instructions that specify a platform, build commands, test commands and each analyzer's configuration parameters. Each analyzer will be run in its own environment (container) after all build and test commands, therefore possible side effects from analyzers will not affect one another.

<div id="toc"></div>

## Platform
Target platform

```
platform: linux # | osx
```

## Build
Build commands

```
build:
- make clean
- make
```

## Test
Test commands

```
test:
- ./hello
```

## Analyzers
Configuration section for each analyzer starts with its name, followed by true/false after a colon. For example, "cpplint: true" indicates that cpplint should be enabled. The configuration parameters on the lines below contain analyzer-specific configs until the next configuration section.

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
