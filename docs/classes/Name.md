---
layout: default
title: "Name class"
parent: "Class reference"
---

# Name Class

**Brief:** universal class for naming symbols

## Detailed description

This class can be used to store symbols name as a string, an operator name or a type.

## Members documentation

### SymbolKind kind() const

**Brief:** returns the kind of symbol that this name names

### const std::string& string() const

**Brief:** returns the name stored as a string

### script::OperatorName operatorName() const

**Brief:** returns the name of the operator

### Type type() const

**Brief:** returns the type associated with this name

