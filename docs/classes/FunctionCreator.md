---
layout: default
title: "FunctionCreator class"
parent: "Class reference"
---

# FunctionCreator Class

## Detailed description

## Members documentation

### Function create(FunctionBlueprint& blueprint, const std::shared_ptr\<ast::FunctionDeclaration>& fdecl, std::vector\<Attribute>& attrs)

**Brief:** creates a function from a blueprint

Parameters:
- the blueprint
- the function declaration
- the attributes

This function creates a function from the blueprint. The function should not be added to its future parent.

The default implementation does not use the attributes and supports a null function declaration.

