# TinyStd
A C++20, single-header alternative standard library with zero dependencies

## Disclaimer

This library is WIP, not actively but sporadically maintained and provides no guarantees whatsoever.

I only made it for myself with just the features I needed and I add them as necessary. Many implementations are incomplete and it is likely that most of what you need is still incomplete or missing. 

You are free to use it for whatever you like, however you like, according to the license.

## What is this?

This library is an alternative standard library for anyone who wants to create software from scratch, without relying on huge libraries with enormous compile time.

This project was directly inspired by Handmade Hero and came to live as a direct consequence.

If you share the Handmade mindset and you want to create bloat-free, fast software from scratch, and you want to work on a higher level than what C provides, then this library serves as your starting point.

### Selling points

- Single Header with ~1000 LOC
- No external dependencies
- No C++ headers
- Only few specific C headers are used
- Optimized for compile time
- Uses C++20 templates and operator overloading where sensible for safe usage
- No RAII
- No Exceptions
- Not a single call to malloc outside of your arena initialization
- Engineered for fast iteration times but not memory safety or fast execution (although that naturally emerged)

### Features

- Purely Arenas for memory management
- Length-Based Strings with `""_s`-literals and methods/operators for manipulation
- Type-safe string formatting (fmt::format/std::format), supporting python-like formatting and custom formatters for your classes
- print function (like printf but with python-like formatting)
- Panic handler
- Optionals
- Result type (Rust/std::expected)
- Lists and Arrays with iterators (for-each)
- Pairs

## Requirements

A C++20 compiler is required.

## Usage

To use this library, simply copy `TinyStd.hpp` into your codebase and include it. Done!

You need one single implementation file, which will contain all the implementations and platform specific code:
```cpp
// TinyStd_impl.cpp
#define TINYSTD_IMPLEMENTATION
#include "TinyStd.hpp"
```

Add this somewhere in your codebase, exactly once.

If you have some sort of build system with a shared module, place it there. To improve compile time, place the implementation site somewhere it is only compiled once.