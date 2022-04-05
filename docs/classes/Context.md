---
layout: default
title: "Context class"
parent: "Class reference"
---

# Context Class

**Brief:** represents the context of evaluation of an expression

## Detailed description

This class represents the context of Engine::eval().

The default constructor constructs a null context (see isNull()). Calling any other function than isNull() on a null context is undefined behavior.

Use addVar() to add variables to the context and clear() to remove to clear the context.

Use exists() to test for the existence of a variable and get() to retrieve the value of a variable.

## Members documentation

### int id() const

**Brief:** returns whether the context id

This function returns -1 if the context isNull().

### bool isNull() const

**Brief:** returns whether the context is null

### Engine* engine() const

**Brief:** returns the context's engine

### const std::string& name() const

**Brief:** returns the context name

### void setName(const std::string& name)

**Brief:** sets the context name

### const std::map\<std::string, Value>& vars() const

**Brief:** returns the variables of the context

### void addVar(const std::string& name, const Value& val)

**Brief:** add a variable to the context

### bool exists(const std::string& name)

**Brief:** returns whether a variable with a given name exists in the context

### Value get(const std::string& name) const

**Brief:** retrieves a value by its name

### void use(const Module& m)

**Brief:** makes the symbols of a module available in the context

### void use(const Script& s)

**Brief:** makes the symbols of a script available in the context

### Scope scope() const

**Brief:** returns the context's scope

This scope is used to resolve names within the expression passed to Engine::eval().

### void clear()

**Brief:** clears the context

