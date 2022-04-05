---
layout: default
title: "Module class"
parent: "Class reference"
---

# Module Class

**Brief:** Provides module features

## Detailed description

## Members documentation

###  Module newSubModule(Args&&... args);()

### Engine* engine() const

**Brief:** Returns the engine that was used to construct this module

### const std::string& name() const

**Brief:** Returns the module name

### bool isNative() const

**Brief:** Returns whether this module is a "native" module.

A "native" module is not implemented by a script.

### Module newSubModule(const std::string& name)

**Brief:** Adds a submodule to this module.

This function creates a submodule that defines no symbol but in which submodule can be added. Use this function if you want to group modules in a common parent module.

### Module newSubModule(const std::string& name, ModuleLoadFunction load, ModuleCleanupFunction cleanup)

**Brief:** Adds a submodule to this module.

This function creates a native submodule. The callbacks load and cleanup are called when the module is loaded and destroyed.

### Module newSubModule(const std::string& name, const SourceFile& src)

**Brief:** Adds a script module to this module.

This function creates a script submodule. When the module is loaded, src is compiled.

### Module getSubModule(const std::string& name) const

**Brief:** Retrieves an existing submodule by name.

### const std::vector\<Module>& submodules() const

**Brief:** Returns the module' submodules.

### bool isLoaded() const

**Brief:** Returns whether the module is loaded.

### void load()

**Brief:** Loads the module.

Throws a ModuleLoadingError on failure. Warning: calling this function while a module is loading is undefined behavior

### Namespace root() const

**Brief:** Returns the module's root namespace

### Scope scope() const

**Brief:** Returns the module's scope.

This scope contains all the symbols that are visible when the module is loaded. This includes submodules (native modules) and symbols exported with and "export import" statement (script modules).

### Script asScript() const

**Brief:** Returns the module's Script.

If the module is a native module, this returns an invalid script.

