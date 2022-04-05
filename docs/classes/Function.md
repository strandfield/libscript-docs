---
layout: default
title: "Function class"
parent: "Class reference"
---

# Function Class

**Brief:** represents a function

## Detailed description

## Members documentation

### const std::string& name() const

**Brief:** returns the function name as a string

Not all functions support this method.

### Name getName() const

**Brief:** returns the function name

### const Prototype& prototype() const

**Brief:** returns the function prototype

### const Type& parameter(size_t index) const

**Brief:** returns the function parameter at a given index

### const Type& returnType() const

**Brief:** returns the function return type

### DefaultArguments defaultArguments() const

**Brief:** Returns the function's default arguments.

Note that you cannot concatenate this list to an existing list of arguments to make a valid call as the default arguments are stored in reverse order; i.e. `defaultArguments()[0]` is the default value for the last parameter, `defaultArguments()[1]` is the default value for the penultimate parameter and so on.

### Script script() const

**Brief:** returns the script in which this function is defined

### Attributes attributes() const

**Brief:** returns the attributes associated to this function

### bool isConstructor() const

**Brief:** returns whether the function is a constructor

### bool isDestructor() const

**Brief:** returns whether the function is a destructor

### bool isDefaultConstructor() const

**Brief:** returns whether the function is a default constructor

### bool isCopyConstructor() const

**Brief:** returns whether the function is a copy constructor

### bool isMoveConstructor() const

**Brief:** returns whether the function is a move constructor

### bool isExplicit() const

**Brief:** returns whether the function is explicit

### bool isConst() const

**Brief:** returns whether the function is a const member function

### bool isVirtual() const

**Brief:** returns whether the function is virtual

### bool isPureVirtual() const

**Brief:** returns whether the function is a pure virtual function

### bool isDefaulted() const

**Brief:** returns whether the function is defaulted

### bool isDeleted() const

**Brief:** returns whether the function is deleted

### bool isMemberFunction() const

**Brief:** returns whether the function is defined in a class

### bool isStatic() const

**Brief:** returns whether the function is static

### bool isSpecial() const

**Brief:** returns whether the function is a constructor or a destructor

### bool hasImplicitObject() const

**Brief:** returns whether the function has an implicit object parameter

In other words, returns whether the function is a non-static member function.

### Class memberOf() const

**Brief:** returns the class this function is a member of

### Namespace enclosingNamespace() const

**Brief:** returns the namespace in which the function is defined

If the function is a member function, this returns the namespace in which the class is defined.

### bool isOperator() const

**Brief:** returns whether the function is an operator

### Operator toOperator() const

**Brief:** returns this function as an operator

### bool isLiteralOperator() const

**Brief:** returns whether the function is a literal operator

### LiteralOperator toLiteralOperator() const

**Brief:** returns this function a literal operator

### bool isCast() const

**Brief:** returns whether the function is a conversion function

### Cast toCast() const

**Brief:** returns this function as a conversion function

### std::shared_ptr\<UserData> data() const

**Brief:** returns the function's user data

### Engine* engine() const

**Brief:** returns the script engine

### Value call(Locals& locals) const

**Brief:** Calls the function with the given locals

This function converts all the locals to the parameter's type before calling invoke().

### Value invoke(std::initializer_list\<Value>&& args) const

**Brief:** Invokes the function with the given args

No conversion nor any type-checking is performed.

### Value invoke(const std::vector\<Value>& args) const

**Brief:** Overloads invoke()

### Value invoke(const Value* begin, const Value* end) const

**Brief:** Overloads invoke()

