---
layout: default
title: "Ast class"
parent: "Class reference"
---

# Ast Class

**Brief:** Represents an abstract syntax tree.

## Detailed description

## Members documentation

### Ast()

**Brief:** Null-constructs an ast

### Ast(const Ast &)

**Brief:** Constructs a new reference to another ast

### ~Ast()

**Brief:** Destructor

### bool isNull() const

**Brief:** Returns whether the Ast is null.

### SourceFile source() const

**Brief:** Returns the ast source file.

### const std::shared_ptr\<ast::Node> & root() const

**Brief:** Returns the ast root node.

### size_t offset(const ast::Node& n) const

**Brief:** returns the offset of a node within the source code

### size_t offset(const parser::Token& tok) const

**Brief:** returns the offset of a token within the source code

### bool isScript() const

**Brief:** Returns whether this is the ast of a Script

### Script script() const

**Brief:** Returns the script associated with this ast.

Note that you can call this function even if isScript() returns false; in such case, a null script is returned.

### const std::vector\<std::shared_ptr\<ast::Statement\>> & statements() const

**Brief:** Returns the top-level statements of the script

Calling this function when isScript() returns false is undefined behavior.

### const std::vector\<std::shared_ptr\<ast::Declaration\>> & declarations() const

**Brief:** Returns the top-level declarations of the script

This returns the subset of statements() for which `Statement::isDeclaration()` returns true.

Calling this function when isScript() returns false is undefined behavior.

### bool isExpression() const

**Brief:** Returns whether this is the ast of an expression

### std::shared_ptr\<ast::Expression> expression() const

**Brief:** Returns the expression associated with this ast

It is safe to call this function even if isExpression() returns false; in such case a null pointer is returned.

