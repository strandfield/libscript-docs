---
layout: default
title: "Locals class"
parent: "Class reference"
---

# Locals Class

**Brief:** Manages a set of local variables

## Detailed description

## Members documentation

### Locals()

### Locals(Locals&& other)

**Brief:** Move constructor

Transfer ownership of all variables in other to the newly constructed Locals object. No copy is performed.

### ~Locals()

**Brief:** Destructor

Destroys all variables in this Locals object that have a reference counter equal to 1.

### void push(const Value& val)

**Brief:** Adds a value to this set of locals

The Value is not copied. The Locals object takes ownership of the Value if its reference count is 1.

### void pop()

**Brief:** Removes the last value added to this set of locals

The Value is destroyed if it is owned by the Locals object.

### Value take()

**Brief:** Removes the last value added to this set of locals

Unlike pop(), the Value is not destroyed; ownership is transferred back to the caller of this function.

### size_t size() const

**Brief:** Returns the number of variables in this object

### const Value& at(size_t index) const

**Brief:** Retrieves a variable in this object

### const std::vector\<Value>& data() const

**Brief:** Returns the internal data

### Locals& operator=(Locals&& other)

**Brief:** Assignment operator

Transfer ownership of all Values in other to this Locals object.

### LocalsProxy operator\[](size_t index)

**Brief:** Provides write access to the locals' variables

### const Value& operator\[](size_t index) const

**Brief:** Array-like access

This is the same as at().

