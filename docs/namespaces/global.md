
# Global namespace

## Classes

- [AstVisitor](classes/AstVisitor.md)
- [AttributesMap](classes/AttributesMap.md)
- [Attributes](classes/Attributes.md)
- [Cast](classes/Cast.md)
- [Class](classes/Class.md)
- [Context](classes/Context.md)
- [DefaultArguments](classes/DefaultArguments.md)
- [DefaultArgumentsMap](classes/DefaultArgumentsMap.md)
- [Engine](classes/Engine.md)
- [Enum](classes/Enum.md)
- [FunctionBlueprint](classes/FunctionBlueprint.md)
- [Function](classes/Function.md)
- [FunctionBuilder](classes/FunctionBuilder.md)
- [GroupModule](classes/GroupModule.md)
- [LegacyModule](classes/LegacyModule.md)
- [LiteralOperator](classes/LiteralOperator.md)
- [ModuleInterface](classes/ModuleInterface.md)
- [Module](classes/Module.md)
- [Name](classes/Name.md)
- [Operator](classes/Operator.md)
- [DelimitersCounter](classes/DelimitersCounter.md)
- [Fragment](classes/Fragment.md)
- [TokenReader](classes/TokenReader.md)
- [Prototype](classes/Prototype.md)
- [DynamicPrototype](classes/DynamicPrototype.md)
- [Scope](classes/Scope.md)
- [ScriptModule](classes/ScriptModule.md)
- [Script](classes/Script.md)
- [SourceFile](classes/SourceFile.md)
- [StringBackend](classes/StringBackend.md)
- [Symbol](classes/Symbol.md)
- [ThisObject](classes/ThisObject.md)
- [Typedef](classes/Typedef.md)
- [Type](classes/Type.md)
- [Value](classes/Value.md)
- [Ast](classes/Ast.md)
- [StandardConversion](classes/StandardConversion.md)
- [FunctionCreator](classes/FunctionCreator.md)
- [FunctionFlags](classes/FunctionFlags.md)
- [Locals](classes/Locals.md)
- [Namespace](classes/Namespace.md)
- [Object](classes/Object.md)
- [TypeSystem](classes/TypeSystem.md)
- [TypeSystemTransaction](classes/TypeSystemTransaction.md)

## Functions

### Visitor::return_type dispatch(Visitor& v, const std::shared_ptr<ast::Node>& n)

**Brief:** performs a virtual-like dispatch of the ast node

Parameters:
- the visitor
- a non-null shared pointer to the ast node

The Visitor class must provide a typedef to a `return_type` and one or more overloads of a `visit` function having the following form:

```
return_type visit(std::shared_ptr<T> node)

  static_assert(std::is_base_of<ast::Node, T>::value);
  ...
```

### Visitor::return_type dispatch(Visitor& v, ast::Node& n)

**Brief:** performs a virtual-like dispatch of the ast node

Parameters:
- the visitor
- a non-const reference to the ast node

This overload works in a similar way as the one taking a shared_ptr but takes a reference instead.

### std::vector<Token> tokenize(const char* src)

**Brief:** tokenize a string

Parameters:
-

### std::vector<Token> tokenize(const char* src, size_t len)

**Brief:** tokenize some characters of a string

Parameters:
-
-

### bool operator==(const Value& lhs, const Value& rhs)

**Brief:** returns whether two Values are the same

Parameters:
-
-

Note that this does not compare the two values for equality but rather whether lhs and rhs have the same memory address.

### bool operator!=(const Value& lhs, const Value& rhs)

**Brief:** returns whether two Values are different

Parameters:
-
-

Note that this does not compare the two values for inequality but rather whether lhs and rhs have a different memory address.

### T& get<T>(const Value& val)

**Brief:** template function to retrieve a value stored in the Value class

Parameters:
-

Calling this function with a type that does not match with the actual type of the value stored in the Value is undefined behavior.

### virtual void AstVisitor::visit(What w, parser::Token tok)

**Brief:** function receiving the children of a node

Parameters:
- enumeration describing the child
- the child token

The default implementation does nothing.

### void recurse(NodeRef n)

**Brief:** performs visitation of the node children

Parameters:
- the node

This effectively calls `ast::visit()` with this visitor and the given node.

### std::shared_ptr<program::Expression> compile(const std::string & cmmd, const Context & con)

**Brief:** Compiles an expression within a context

Parameters:
-
-

Throws CompilationFailure if the compilation fails

### DefaultArgumentVector process_default_arguments(ExpressionCompiler& ec, const std::vector<ast::FunctionParameter>& params, const Function& f)

**Brief:** computes the default arguments of a function

Parameters:
-
-
-

### void fill_prototype(FunctionBlueprint& blueprint, const std::shared_ptr<ast::FunctionDecl>& fundecl, const Scope& scp)

**Brief:** fills the prototype field of a function blueprint

Parameters:
- the function blueprint to fill
- the function declaration in the ast
- the scope in which name are resolved

### NameLookup resolve_name(const std::shared_ptr<ast::Identifier>& name, const Scope& scp)

**Brief:** resolves a name within a given scope

Parameters:
-
-

### Type resolve_type(const ast::QualifiedType& qt, const Scope& scp)

**Brief:** resolves a type within a scope

Parameters:
- the qualified type
- the resolution scope

### int precedence(OperatorName op)

**Brief:** returns the precedence group of an operator

Parameters:
- the name of an operator

For any valid operator name, this function returns the precedence group of the operator. This is a value between 1 and 15 with 1 being the operator of highest precedence and 15 of lowest precedence.

### Associativity associativity(int group)

**Brief:** returns the associativity of a an operator given its group

Parameters:
- the id of a precedence group

The input parameter must be a value returned by the function precedence().

