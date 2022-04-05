---
layout: default
title: "Engine class"
parent: "Class reference"
---

# Engine Class

**Brief:** Script engine class

## Detailed description

## Members documentation

### Type registerType(std::string name)

**Brief:** register a new type

### Type registerType(std::string name, Type::TypeFlag what)

**Brief:** register a new type

Parameters:
- the name of the type
- whether the type is enum or class

### Type registerType()

**Brief:** register a new type

### Type getType() const

**Brief:** get a type

Throws UnknownTypeError if the type wasn't previously registered with registerType().

### Type makeType() const

**Brief:** constructs a Type from a C++ type

This function may use getType() and as such can raise an UnknownTypeError.

### Engine()

**Brief:** default constructor

You must call setup() before using the engine.

### ~Engine()

**Brief:** Destroys the script engine

This function calls tearDown().

### void setup()

**Brief:** setups the script engine

### void tearDown()

**Brief:** destroys the engine

This function destroys the global namespace and all the modules.

### TypeSystem* typeSystem() const

**Brief:** Returns the engine's typesystem.

### Type getType(const std::string& name)

**Brief:** retrieves a type by its name

Note that the type must have been previsouly registered with registerType().

### Value newBool(bool bval)

**Brief:** Constructs a new value of type bool

### Value newChar(char cval)

**Brief:** Constructs a new value of type char

### Value newInt(int ival)

**Brief:** Constructs a new value of type int

### Value newFloat(float fval)

**Brief:** Constructs a new value of type float

### Value newDouble(double dval)

**Brief:** Constructs a new value of type double

### Value newString(const String & sval)

**Brief:** Constructs a new value of type String

### Array newArray(ArrayType array_type)

**Brief:** Constructs a new array with the given array-type

Parameters:
- type of the array

This function returns an object of type Array, any array can be converted to a Value using Value::fromArray().

###  Array newArray(ElementType element_type, ...);()

**Brief:** Constructs a new array with the given element-type

If no such array-type with the given element-type exists, it is instantiated. You can call this function with the additional argument `Engine::FailIfNotInstantiated` to make this function throw in such case.

### Value construct(Type t, const std::vector\<Value> & args)

**Brief:** Constructs a new value of the given type with the provided arguments.

Parameters:
- type of the value to construct
- arguments to be passed the constructor

If `t` is a fundamental type, at most one argument may be provided in `args`. If `t` is an enum type, a value of the same type must be provided. If `t` is an object type, overload resolution is performed to select a suitable constructor.

On failure, this function throws a ConstructionError with a code describing the error (e.g. NoMatchingConstructor, ConstructorIsDeleted, TooManyArgumentInInitialization, ...).

### void destroy(Value val)

**Brief:** Destroys a value.

Parameters:
- value to destroy

By calling this function, you also implicitly transfer ownership of the value back to the engine; this means that you shouldn't use the value any further.

### bool canCopy(const Type & t)

**Brief:** Returns whether a type is copyable.

Parameters:
- input type

This function internally asks TypeSystem::isCopyConstructible().

### Value copy(const Value & val)

**Brief:** Creates a copy of a value.

Parameters:
- input value

Throws CopyError on failure. This may happen if the type has a deleted or no copy constructor.

### bool canConvert(const Type & srcType, const Type & destType)

**Brief:** Checks if a conversion is possible.

Parameters:
- source type
- dest type

### Value convert(const Value & val, const Type & destType)

**Brief:** Converts a value to the given type.

Parameters:
- input value
- dest type

Throws ConversionError on failure.

### Namespace rootNamespace() const

**Brief:** Returns the global namespace.

### compiler::Compiler* compiler() const

**Brief:** Returns the engine's compiler.

### interpreter::Interpreter* interpreter() const

**Brief:** Returns the engine's interpreter.

### Script newScript(const SourceFile & source)

**Brief:** Creates a new script with the given source.

Parameters:
- source file

### bool compile(Script s, CompileMode mode)

**Brief:** Compiles a script.

Parameters:
- input script
- compilation mode

### void destroy(Script s)

**Brief:** Destroys a script.

Parameters:
- input script

### Module newModule(const std::string & name)

**Brief:** Creates a new native module.

Parameters:
- module name

### Module newModule(const std::string & name, ModuleLoadFunction load, ModuleCleanupFunction cleanup)

**Brief:** Creates a new native module.

Parameters:
- module name
- load function
- cleanup function

### Module newModule(std::string name, const SourceFile& src)

**Brief:** Creates a new script module.

Parameters:
- module name
- load function

### const std::vector\<Module> & modules() const

**Brief:** Returns all existing modules.

### Module getModule(const std::string & name)

**Brief:** Returns the module with the given name.

Parameters:
- module name

### Type typeId(const std::string & typeName, const Scope & scope) const

**Brief:** Searchs for a type by name.

Parameters:
- type name
- scope

Throws UnknownTypeError if the type could not be resolved.

### std::string toString(const Type& t) const

**Brief:** Computes a string representation of the given type.

Parameters:
- type

### std::string toString(const Function& f) const

**Brief:** Computes a string representation of the function prototype.

Parameters:
- function

### Context newContext()

**Brief:** Creates a new context.

### Context currentContext() const

**Brief:** Returns the current context.

### void setContext(Context con)

**Brief:** Sets the current context.

Parameters:
- the context

### Value eval(const std::string & command)

**Brief:** Evaluates an expression.

Parameters:
- input command

The currentContext() is used to evaluate the expression.

Throws EvaluationError on failure.

### const std::vector\<Script> & scripts() const

**Brief:** Returns all list of all existing scripts.

