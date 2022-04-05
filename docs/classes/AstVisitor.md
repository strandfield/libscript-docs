---
layout: default
title: "AstVisitor class"
parent: "Class reference"
---

# AstVisitor Class

**Brief:** generic ast visitor

## Detailed description

This class can be used to traverse an abstract syntax tree (AST) in a generic way, i.e. without considering the actual type of the ast nodes.

## Members documentation

### virtual void visit(What w, NodeRef n) = 0

**Brief:** function receiving the children of a node

Parameters:
- enumeration describing the child
- the child

### void visit(AstVisitor& visitor, NodeRef node)

**Brief:** feed the visitor with the children of an ast node

Parameters:
- the visitor
- non-null shared pointer to the node

