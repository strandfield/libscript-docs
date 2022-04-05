---
layout: default
title: "TypeSystemTransaction class"
parent: "Class reference"
---

# TypeSystemTransaction Class

**Brief:** Provides safe way to modify the type-system.

## Detailed description

## Members documentation

### TypeSystemTransaction(TypeSystem* ts)

**Brief:** Constructs a transaction object.

If ts is not null, starts a transaction.

### ~TypeSystemTransaction()

**Brief:** Destroys the transaction object

If there are uncaught exceptions and isActive() is true, this calls rollback(), otherwise this calls commit().

### bool isActive() const

**Brief:** Returns whether the transaction is active.

### void start()

**Brief:** Starts a transaction on the typesystem passed through the constructor.

### void start(TypeSystem* ts)

**Brief:** Starts a transaction on the given typesystem.

### void commit()

**Brief:** Ends the currently active transaction and validate all changes.

### void commit()

**Brief:** Reverse all changes made since the beginning of the transaction.

