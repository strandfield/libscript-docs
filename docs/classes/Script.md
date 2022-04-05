---
layout: default
title: "Script class"
parent: "Class reference"
---

# Script Class

**Brief:** represents an executable script

## Detailed description

`

## Members documentation

### bool isNull() const

**Brief:** returns whether this instance is null

### bool isCompiled() const

**Brief:** returns whether the script was compiled

### int id() const

**Brief:** returns the script's id

### const std::string& path() const

**Brief:** returns the script's filepath

### bool compile(CompileMode mode, FunctionCreator* fcreator)

**Brief:** Compiles the script

Returns true on success, false otherwise. If the compilation failed, use messages() to retrieve the error messages. Warning: Calling this function while a script is compiling is undefined behavior.

### bool isReady() const

**Brief:** returns whether the script is ready to be executed

### void run()

**Brief:** runs the script

The script must have been compiled beforehand. Calling run() on a script for which isReady() is false will result in an exception being thrown.

### void clear()

**Brief:** clears the script

### const SourceFile& source() const

**Brief:** returns the script' source

### Namespace rootNamespace() const

**Brief:** returns the script's root namespace

### const std::map\<std::string, int>& globalNames() const

**Brief:** returns the name of the global variables defined in the script

### const std::vector\<Value>& globals() const

**Brief:** returns the script's global variables

This vector is filled during a call to run().

### const std::vector\<diagnostic::DiagnosticMessage>& messages() const

**Brief:** returns the diagnostic messages produced while compiling the script

### Scope exports() const

**Brief:** returns the script exported symbols

### DefaultArguments getDefaultArguments(const Function& f) const

**Brief:** returns the default arguments for a given function

### Ast ast() const

**Brief:** Returns the script ast.

### void clearAst()

**Brief:** Destroys the script ast.

Note that this does nothing if the ast is marked as locked. An ast is locked by the implementation when it may be needed later in time; for example when the script contains templates.

### std::vector\<std::pair\<Function, std::shared_ptr\<program::Breakpoint\>>> breakpoints(int line) const

**Brief:** returns breakpoints associated to a given line from the script

### Engine* engine() const

**Brief:** returns the script's engine

