---
layout: default
title: "Symbol class"
parent: "Class reference"
---

# Symbol Class

**Brief:** provides storage for any symbol (class, namespace, etc...)

## Detailed description

## Members documentation

### explicit Symbol(const Class& c)

**Brief:** constructs a symbol from a class

### explicit Symbol(const Namespace& n)

**Brief:** constructs a symbol from a namespace

### Symbol(const Function& f)

**Brief:** constructs a symbol from a function

### Engine* engine() const

**Brief:** returns the script engine

### Symbol::Kind kind() const

**Brief:** returns the symbol's kind

### bool isClass() const

**Brief:** returns whether the symbol is a class

### Class toClass() const

**Brief:** retrieves the symbol as a class

### bool isNamespace() const

**Brief:** returns whether the symbol is a namespace

### Namespace toNamespace() const

**Brief:** retrieves the symbol as a namespace

### bool isFunction() const

**Brief:** returns whether the symbol is a function

### Function toFunction() const

**Brief:** retrieves the symbol as a function

### Name name() const

**Brief:** returns the symbol's name

### Symbol parent() const

**Brief:** returns this symbol's parent

### Script script() const

**Brief:** returns the script in which the symbol is defined

### Attributes attributes() const

**Brief:** returns the attributes associated to the symbol

