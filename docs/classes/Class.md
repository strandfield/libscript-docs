---
layout: default
title: "Class class"
parent: "Class reference"
---

# Class Class

**Brief:** represents a class

## Detailed description

## Members documentation

### bool isNull() const

**Brief:** returns whether the class is null

Calling any other function than isNull() on a null class is undefined behavior.

### int id() const

**Brief:** returns the class' id

### const std::string& name() const

**Brief:** returns the class name

### Class parent() const

**Brief:** returns the base class of this class

### bool inherits(const Class& type) const

**Brief:** returns whether this class is derived from a given class

This function returns true if this class is derived directly or indirectly from type.

### int inheritanceLevel(const Class& type) const

**Brief:** returns the level of inheritance of this class to a given class

If this class is not derived from type, this function returns -1; otherwise, this function returns the depth between this class and type in the inheritance tree.

A return value of 0 indicates that this class equals type ; a return value of 1 indicates a direct inheritance; and so on.

### bool isFinal() const

**Brief:** returns whether this class is final

### Class indirectBase(int n) const

**Brief:** returns a base of this class

If n is negative or null, this class is returned. If n is 1, this returns this class' base class. If n is 2, this returns the base class this class' base; and so on.

@TODO: rename ?

### bool isClosure() const

**Brief:** returns whether this class is a closure type

### ClosureType toClosure() const

**Brief:** returns this class as a closure type

### const std::vector\<Class::DataMember>& dataMembers() const

**Brief:** returns the data members of this class

This does not include the data members of the base class.

### int cumulatedDataMemberCount() const

**Brief:** returns the cumulated count of data members

This returns the size of dataMembers() plus the number of data members in all base classes.

### int attributesOffset() const

**Brief:** returns the offset of this class' data members

### int attributeIndex(const std::string& attrName) const

**Brief:** returns the index of a data member given its name

The data members of the base classes are considered by this function.

### Script script() const

**Brief:** returns the script in which this class is defined

If the class wasn't defined in a script, this function returns a null Class.

### const std::shared_ptr\<UserData>& data() const

brief returns the user data associated to this class

### Value instantiate(const std::vector\<Value>& args)

**Brief:** creates a object of this class

### const std::vector\<Class>& classes() const

**Brief:** returns the classes defined in this class

Note that this is not the list of classes that are derived from this class.

### const std::vector\<Enum>& enums() const

**Brief:** returns the enums defined in this class

### const std::vector\<Template>& templates() const

**Brief:** returns the templates defined in this class

### void addTypedef(Typedef t)

**Brief:** adds a typedef to the class

### const std::vector\<Typedef>& typedefs() const

**Brief:** returns the list of typedef in this class

### const std::vector\<Operator>& operators() const

**Brief:** returns the operators defined in this class

### const std::vector\<Cast>& casts() const

**Brief:** returns the conversion functions defined in this class

### const std::vector\<Function>& memberFunctions() const

**Brief:** returns the methods defined in this class

Note that this does not include the operators, conversion functions, constructors and destructor.

@TODO: rename to methods() ?

### void addMethod(const Function& f)

**Brief:** adds a method to this class

This functions does not support adding operators, constructors, conversion functions; use addFunction() instead.

### void addFunction(const Function& f)

**Brief:** adds a function to this class

### bool isAbstract()

**Brief:** returns whether this class is an abstract class

An abstract class has at least one virtual pure function.

### const std::vector\<Function>& vtable() const

**Brief:** returns the vtable

### const std::vector\<Function>& constructors() const

**Brief:** returns the class' constructors

### Function defaultConstructor() const

**Brief:** returns the class default constructor

### bool isDefaultConstructible() const

**Brief:** returns whether the class is default constructible

### Function copyConstructor() const

**Brief:** returns the class copy constructor

### bool isCopyConstructible() const

**Brief:** returns whether the class is copy constructible

### Function moveConstructor() const

**Brief:** returns the class move constructor

### bool isMoveConstructible() const

**Brief:** returns whether the class is move constructible

### Function destructor() const

**Brief:** returns the class destructor

### void addStaticDataMember(const std::string& name, const Value& value, AccessSpecifier aspec)

**Brief:** add a static data member to the class

### const std::map\<std::string, Class::StaticDataMember>& staticDataMembers() const

**Brief:** returns the class static data members

### void addFriend(const Function& f)

**Brief:** add a friend function to the class

### void addFriend(const Class& c)

**Brief:** add a friend class to the class

### const std::vector\<Function>& friends(const Function&) const

**Brief:** returns the class friend functions

### const std::vector\<Function>& friends(const Class&) const

**Brief:** returns the class friend classes

### Class memberOf() const

**Brief:** returns the class in which this class is defined

### Namespace enclosingNamespace() const

**Brief:** returns the namespace in which this class is defined

### Engine* engine() const

**Brief:** returns the script engine

