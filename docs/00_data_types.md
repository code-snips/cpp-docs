# Data Types

Primitive data types are the foundation of programming in C++. They allow you to perform a variety of operations and store data in your programs. This tutorial covers the basics of primitive data types in modern C++, their sizes, ranges, and how to use them effectively.

## Integer Types

Integer types are used to store whole numbers, both positive and negative.

### int

The `int` type is the most commonly used integer type. It's suitable for values without a fractional component.

```cpp
int a = 5;
int b = -5;
```

- **Size**: Typically 4 bytes (32 bits).
- **Range**: -2,147,483,648 to 2,147,483,647 on most systems.

### short

The `short` type is used for smaller integers. It consumes less memory.

```cpp
short s = 32767;
```

- **Size**: 2 bytes (16 bits).
- **Range**: -32,768 to 32,767.

### long

The `long` type is used for integers larger than `int`.

```cpp
long l = 2147483647;
```

- **Size**: Typically 4 bytes (32 bits) on 32-bit systems and 8 bytes (64 bits) on 64-bit systems.
- **Range**: -2,147,483,648 to 2,147,483,647 on 32-bit systems; -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 on 64-bit systems.

### long long

The `long long` type is for very large integers.

```cpp
long long ll = 9223372036854775807;
```

- **Size**: 8 bytes (64 bits).
- **Range**: -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.

## Floating Point Types

Floating-point types can represent numbers with fractional parts.

### float

The `float` type represents single-precision floating-point numbers.

```cpp
float f = 3.14f;
```

- **Precision**: About 7 decimal digits.
- **Range**: Approximately 1.2E-38 to 3.4E+38.

### double

The `double` type represents double-precision floating-point numbers.

```cpp
double d = 3.141592653589793;
```

- **Precision**: About 15 decimal digits.
- **Range**: Approximately 2.3E-308 to 1.7E+308.

### long double

The `long double` type provides extended precision for floating-point numbers.

```cpp
long double ld = 3.141592653589793238462643383279502884L;
```

- **Precision and Range**: Varies, typically more than `double`.

## Character Type

### char

The `char` type is used to store single characters.

```cpp
char c = 'A';
```

- **Size**: 1 byte (8 bits).
- **Range**: -128 to 127 for signed, 0 to 255 for unsigned.

## Boolean Type

### bool

The `bool` type is used to store true or false values.

```cpp
bool b = true;
```

- **Size**: Typically 1 byte (8 bits).
- **Values**: `true` (1) or `false` (0).