---
layout: default
title: "Scope class"
parent: "Class reference"
---

# Scope Class

**Brief:** represents a scope

## Detailed description

Scopes are used to resolve names.

Depending on the scope, the same name may identify different entities.

## Members documentation

### Scope(const Enum& e, const Scope& parent)

**Brief:** construct a scope from an enum

### Scope(const Class& cla, const Scope& parent)

**Brief:** construct a scope from a class

### Scope(const Namespace& na, const Scope& parent)

**Brief:** construct a scope from a namespace

### Scope(const Script& s, const Scope& parent)

**Brief:** construct a scope from a script

### bool isNull() const

**Brief:** returns whether this scope is null

### Scope::Type type() const

**Brief:** returns the scope's type

### Engine* engine() const

**Brief:** returns the script engine

### bool hasParent() const

**Brief:** returns whether the scope as a parent scope

### Scope parent() const

**Brief:** returns the parent of this scope

### bool isClass() const

**Brief:** returns whether this scope is a class

### bool isNamespace() const

**Brief:** returns whether this scope is a namespace

### bool isScript() const

**Brief:** returns whether this scope is a script

### Class asClass() const

**Brief:** returns this scope as a class

### Namespace asNamespace() const

**Brief:** returns this scope as a namespace

### Enum asEnum() const

**Brief:** returns this scope as an enumeration

### Script asScript()

**Brief:** returns this scope as a script

### Symbol symbol() const

**Brief:** returns the symbol that is enclosing this scope

### Script script() const

**Brief:** Returns the script that contains this scope

### const std::vector\<Class>& classes() const

**Brief:** returns the classes in this scope

### const std::vector\<Enum>& enums() const

**Brief:** returns the enums in this scope

### const std::vector\<Function>& functions() const

**Brief:** returns the functions in this scope

### const std::vector\<Namespace>& namespaces() const

**Brief:** returns the namespaces in this scope

### const std::vector\<Operator>& operators() const

**Brief:** returns the operators in this scope

### const std::vector\<LiteralOperator>& literalOperators() const

**Brief:** returns the literal operators in this scope

### const std::vector\<Template>& templates() const

**Brief:** returns the templates in this scope

### AccessSpecifier accessibility() const

### std::vector\<Function> operators(OperatorName op) const

**Brief:** get all operators of a given name in this scope

This function only returns operators in this scope and excludes operators from the parent scope.

### Scope child(const std::string& name) const

**Brief:** returns a child scope of this scope

### void inject(const std::string& name, const script::Type& t)

**Brief:** inject a type alias in this scope

### void inject(const Class& cla)

**Brief:** inject a class in this scope

### void inject(const Enum& e)

**Brief:** inject an enum in this scope

### void inject(const Scope& scp)

**Brief:** inject a namespace scope in this scope

### void merge(const Scope& scp)

**Brief:** merge with another scope

TODO: clarify difference with inject()

### void inject(const NamespaceAlias& alias)

**Brief:** inject a namespace alias in this scope

### static Namespace enclosingNamespace(const Type& t, Engine* e)

**Brief:** Return the enclosing namespace of the given type.

### std::vector\<Function> lookup(const LiteralOperator&, const std::string& suffix) const

**Brief:** lookup literal operators with a given suffix

This will search for literal operators in this scope, and, if none was found, in the parent scope.

### std::vector\<Function> lookup(OperatorName op) const

**Brief:** lookup operators with a given name

This will search for operators in this scope, and, if none was found, in the parent scope.

### NameLookup lookup(const std::string& name) const

**Brief:** perform name lookup in this scope

