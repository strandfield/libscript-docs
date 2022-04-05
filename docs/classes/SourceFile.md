---
layout: default
title: "SourceFile class"
parent: "Class reference"
---

# SourceFile Class

**Brief:** Represents a source file.

## Detailed description

The SourceFile class represents a source file for a Script. The actual source can currently be either a file on the local file system or an in-memory string (see fromString() method).

The scripting engine assumes that source files are encoded in UTF-8, and thus uses a std::string as the underlying storage type.

If the input is a local file, it is not loaded until load() is called. After a call to load(), the entire file is stored in memory. Memory can be released by calling unload() unless the source file isLocked(), meaning that the system needs the source to be available (this is the case, for example, if your script contains templates).

The SourceFile class is an implicitely shared class: it can be null constructed and copy and assignment do not create true copies but rather new reference to the same object.

## Members documentation

### SourceFile()

**Brief:** Null-constructs a source file.

The only thing you can do safely on a null source file is to test for nullity.

### SourceFile(const std::string & path)

**Brief:** Constructs a sourcefile.

Parameters:
- path on the local file system

### SourceFile(const std::shared_ptr\<SourceFileImpl> & impl)

**Brief:** Constructs a sourcefile from its implementation).

Parameters:
- implementation

### bool isNull() const

**Brief:** Returns whether this source file is null.

### const std::string & filepath() const

**Brief:** Returns the filepath of this sourcefile.

If the source file was constructed using fromString(), this returns an empty string.

### SourceFile::Position SourceFile::map(Offset off) const

**Brief:** maps an offset to a (line, column)

Parameters:
- an offset in the file

### void load()

**Brief:** Loads the source file.

This does nothing if the sourcefile is already loaded or if it was created from an in-memory string. Throws std::runtime_error on failure.

### bool isLoaded() const

**Brief:** Returns whether the sourcefile is loaded.

### bool isLocked() const

**Brief:** Returns whether the sourcefile is locked.

A source file is locked by the system if it needs the source to be available later after a script has been compiled.

### void unload()

**Brief:** Unloads the source file.

This does nothing if the source file is locked.

