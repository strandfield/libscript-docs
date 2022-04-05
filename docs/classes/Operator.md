---
layout: default
title: "Operator class"
parent: "Class reference"
---

# Operator Class

## Detailed description

## Members documentation

### Type input() const

**Brief:** returns the input type of this literal operator

### Type output() const

**Brief:** returns the output type of this literal operator

### const std::string& suffix() const

**Brief:** returns the suffix of this literal operator

### OperatorName operatorId() const

**Brief:** returns the operator name

### bool isBinary() const

**Brief:** returns whether the operator is a binary operator

### static bool isBinary(BuiltInOperator op)

**Brief:** returns whether the operator is a binary operator

### static bool isUnary(BuiltInOperator op)

**Brief:** returns whether the operator is an unary operator

### static bool onlyAsMember(BuiltInOperator op)

**Brief:** returns whether the operator can only be defined as a member

### static int precedence(BuiltInOperator op)

**Brief:** returns the precedence of an operator

### static Associativity associativity(int group)

**Brief:** returns the associativity of an operator given its precedence group

### Type firstOperand() const

**Brief:** returns the first operand of the operator

### Type secondOperand() const

**Brief:** returns the second operand of the operator

### static const std::string& getSymbol(BuiltInOperator op)

**Brief:** returns a string representation of the operator

