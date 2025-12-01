# C++ JSON Library Demo

This demo showcases all features of the modern C++ JSON library.

## Compilation Instructions

To compile the demo program, use the following g++ command:

```bash
g++ -std=c++20 -I./src demo/json_demo.cpp -o json_demo.exe && ./json_demo.exe
```

## Running the Demo

After successful compilation, run the demo with:

```bash
./json_demo.exe
```

The output should be:

```
JSON Library Demo
=================

=== Testing Basic Types ===
String: "Hello, World!"
Integer: 42
Real number: 3.14159
Boolean true: true
Boolean false: false
Null: null

=== Testing Objects ===
Person object: {
  "active": true,
  "age": 30,
  "name": "John Doe",
  "nickname": null,
  "salary": 75000.5
}
Person with nested address: {
  "active": true,
  "address": {
    "city": "Anytown",
    "street": "123 Main St",
    "zip": "12345"
  },
  "age": 30,
  "name": "John Doe",
  "nickname": null,
  "salary": 75000.5
}

=== Testing Arrays ===
Fruits array: [
  "apple",
  "banana",
  "cherry"
]
Mixed type array: [
  "text",
  42,
  3.14,
  true,
  null
]

=== Testing Fluent Builder ===
Person (fluent): {
  "active": true,
  "age": 28,
  "middle_name": null,
  "name": "Jane Smith",
  "salary": 85000
}
Colors array (fluent): [
  "red",
  "green",
  "blue",
  42,
  true
]

=== Testing Literal Operators ===
String literal: "Hello, World!"
Integer literal: 42
Real literal: 3.14159

=== Testing Convenience Builders ===
Convenience object: {
  "active": true,
  "type": "convenience",
  "value": 123
}
Convenience array: [
  "one",
  "two",
  "three"
]

=== Testing Complex Structure ===
Complex company structure: {
  "active": true,
  "departments": [
    {
      "budget": 1000000,
      "employees": [
        {
          "name": "Alice Johnson",
          "position": "Software Engineer",
          "salary": 95000
        },
        {
          "name": "Bob Smith",
          "position": "Product Manager",
          "salary": 105000
        }
      ],
      "name": "Engineering"
    },
    {
      "budget": 500000,
      "employees": [
        {
          "name": "Carol White",
          "position": "Sales Manager",
          "salary": 80000
        }
      ],
      "name": "Sales"
    }
  ],
  "founded": 2010,
  "name": "Tech Corp"
}

Demo completed successfully!
```

## Features Demonstrated

The demo program demonstrates the following features:

1. **Basic JSON Types**
   - Strings
   - Numbers (integers and real numbers)
   - Booleans (true/false)
   - Null values

2. **JSON Objects**
   - Creating objects with key-value pairs
   - Nested objects
   - Object manipulation

3. **JSON Arrays**
   - Creating arrays
   - Mixed-type arrays
   - Array manipulation

4. **Fluent Builder API**
   - Chain method calls for building JSON structures
   - Object and array builders
   - Type-safe construction

5. **Literal Operators**
   - String literals: `"text"_json`
   - Integer literals: `42_json`
   - Real number literals: `3.14_json`

6. **Convenience Builders**
   - `object_builder()` for creating objects
   - `array_builder()` for creating arrays
   - Type-safe fluent interface

7. **Type Checking**
   - Runtime type checking methods
   - Safe type introspection

8. **Complex Structures**
   - Nested objects and arrays
   - Real-world JSON examples

## Library Design

The library follows modern C++ practices:

- **RAII**: Automatic memory management
- **Smart Pointers**: No manual memory management
- **Exceptions**: Safe error handling
- **Namespaces**: Organized code structure
- **C++20 Features**: Modern language features

## Error Handling

The library uses exceptions for error handling. All operations are designed to be exception-safe.

## Dependencies

- C++20 compatible compiler
- Standard library only (no external dependencies)
