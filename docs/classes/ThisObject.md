---
layout: default
title: "ThisObject class"
parent: "Class reference"
---

# ThisObject Class

**Brief:** Convenience class providing initialization/destruction utilities.

## Detailed description

This class is a helper class that is used during Value initialization and destruction. Instances of this class are returned by the thisObject() member of FunctionCall.

## Members documentation

###  void init\<T>(Args &&...);()

**Brief:** initializes this with a C++ object

### void init()

**Brief:** Initialize the object

After initialization, the toObject() method of Value returns a valid Object.

### void push(const Value& val)

**Brief:** Adds a data member to the object

This method should be called after init().

### Value pop()

**Brief:** Takes ownership of the latest data member.

### void destroy()

**Brief:** Destroys all data members of the object.

