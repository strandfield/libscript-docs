---
layout: default
title: "ModuleInterface class"
parent: "Class reference"
---

# ModuleInterface Class

**Brief:** abstract base class for all modules

## Detailed description

## Members documentation

### virtual bool is_loaded() const = 0

**Brief:** returns whether the module is loaded

### virtual void load() = 0

**Brief:** loads the module

### virtual Namespace get_global_namespace() const = 0

**Brief:** returns the root of the module's symbol tree

### Engine* engine() const

**Brief:** returns a pointer to the engine

### const std::string& name() const

**Brief:** returns the module's name

### ModuleInterface(Engine* e, std::string name)

**Brief:** constructs a module with the given name

### ~ModuleInterface()

**Brief:** destroys the module

### virtual void unload()

**Brief:** unloads the module

This function should be reimplemented in a subclass if necessary. The default implementation does nothing.

### virtual Script get_script() const

**Brief:** returns the script associated with this module

The default implementation returns an invalid script.

### virtual const std::vector\<Module>& child_modules() const

**Brief:** returns the module's child

The default implementation returns an empty vector.

### virtual void add_child(Module m)

**Brief:** adds a child module to this module

The default implementation does nothing.

### void attach(Namespace& ns)

**Brief:** attach a namespace to this module

This will make the module easily retrievable from the namespace. This function must not be called from the constructor.

### void attach(Script& s)

**Brief:** attach a script to this module

This will make the module easily retrievable from the script. This function must not be called from the constructor.

### Namespace createRootNamespace()

**Brief:** creates a root namespace for this module

A namespace created with this function is in no significant way different from any other namespace; the difference is that it is linked to this module so that the module can be retrieved from the namespace.

This function must not be called from the constructor.

### Script createScript(const SourceFile& src)

**Brief:** creates a script for this module

This function must not be called from the constructor.

### void compile(Script& s)

**Brief:** compiles the script

Depending on whether a script is currently being compiled, this function will either compile the script immediately or add it to the current compile session.

