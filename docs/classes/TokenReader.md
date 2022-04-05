---
layout: default
title: "TokenReader class"
parent: "Class reference"
---

# TokenReader Class

**Brief:** basic facility for consuming tokens

## Detailed description

## Members documentation

### TokenReader(const char* src, const std::vector\<Token>& tokens)

**Brief:** constructs a token reader from a list of tokens

Parameters:
- the source string for the tokens
- the token list

### bool atEnd() const

**Brief:** returns whether all tokens have been read

### Token read()

**Brief:** reads the next token

Note that this function throws SyntaxError if no more token is available.

### Token unsafe_read()

**Brief:** reads the next token without bounds checking

Use this function only after checking that atEnd() returns false.

### Token read(const Token::Id& type)

**Brief:** reads a particular token

Parameters:
- the type of the token to read

This function throws SyntaxError if no token are available or if the token is not of the requested type.

### Token peek() const

**Brief:** returns the next token without consuming it

Successive calls to peek() return the same token. Call read() to get the current token and go to the next.

### Token peek(size_t n) const

**Brief:** look ahead a token

Parameters:
- number of token to skip

### Token unsafe_peek() const

**Brief:** returns the current token without performing bounds checking

### void seek(Fragment::iterator it)

**Brief:** moves the reading cursor

Parameters:
- iterator to the token to set as current

### TokenReader subfragment() const

**Brief:** returns a token reader working on a subrange of tokens

### bool operator==(const TokenReader& lhs, const TokenReader& rhs)

**Brief:** compares two token readers for equality

Two token readers are considered equal if the work on the same range of tokens and if the current cursor is at the same token.

### bool operator!=(const TokenReader& lhs, const TokenReader& rhs)

**Brief:** compares two token readers for inequality

