# Repository Map

```markdown
/ (jansson-converted)
├── .git/
├── demo/
    ├── README.md (Markdown)
    └── json_demo.cpp (C++)
        └── Description: Helper function to print JSON values Test basic JSON types String Integer Real number Boolean Null Test JSON objects Simple object Nested object Test JSON arrays Simple array Mixed type array Test fluent builder interface Build object with fluent interface Build array with fluent interface Test literal operators Test convenience builders Object builder Array builder Test complex nested structure
├── src/
    ├── error.cpp (C++)
    ├── error.hpp (C++)
    ├── hashtable.cpp (C++)
    │   └── Description: StringHash implementation Use the same hash function as the original jansson Explicit instantiation for json_t*
    ├── hashtable.hpp (C++)
    │   └── Description: Forward declaration Hash function wrapper for std::string Thread-safe HashTable implementation using std::unordered_map Internal storage type Container for ordered iteration Forward iterator class Const iterator class Convert from iterator to const_iterator Constructors and destructor Assignment operators Element access Iterators Capacity Modifiers Lookup Hash policy Thread safety Legacy API compatibility Iterator-based legacy API Memory resource access Specialization for json_t* to handle reference counting ... (same interface as above, but with json_t* specific implementations) Type aliases for common use cases Free functions
    ├── hashtable_impl.hpp (C++)
    │   └── Description: Iterator implementations for HashTable<json_t*, std::shared_mutex> Const iterator implementations Iterator factory functions
    ├── hashtable_seed.cpp (C++)
    │   └── Description: Global hash table seed Initialize the hash table seed Generate a random seed if none provided Static initialization This will initialize the seed before main() is called
    ├── hashtable_seed.hpp (C++)
    │   └── Description: Global hash table seed for consistent hashing across the application Initialize the hash table seed Get the current hash table seed RAII wrapper for hash seed initialization Non-copyable Non-movable
    ├── hashtable_simple.cpp (C++)
    │   └── Description: Constructor and destructor Move constructor and assignment Core operations Update existing value Insert new value Size and capacity Thread safety Iterator implementations Iterator functions Private helper methods Free functions
    ├── hashtable_simple.hpp (C++)
    │   └── Description: Hash function wrapper for std::string Thread-safe HashTable implementation that replaces the C hashtable_t Internal storage type Container for ordered iteration (to maintain compatibility) Constructor and destructor Non-copyable but movable Core operations (compatible with C API) C++ friendly overloads Size and capacity Thread safety Iterator support (for compatibility) Iterator functions (for compatibility) Legacy iterator functions Friend functions Free functions
    ├── jansson.h (C++)
    ├── jasson.hpp (C++)
    │   └── Description: Convenience functions for type checking and casting Type checking functions Equality functions Copy functions
    ├── json_config.hpp (C++)
    │   └── Description: Define json_int_t as int64_t for better portability
    ├── json_convenience.hpp (C++)
    │   └── Description: Convenience functions for common operations Create a JSON value from any type Specializations for common types Convert JSON value to C++ type Specializations for common types Convenience builder functions Convenience functions for common operations
    ├── json_dumper.cpp (C++)
    │   └── Description: UTF-16 surrogate pair Use the object's address as a unique key Convenience functions
    ├── json_dumper.hpp (C++)
    │   └── Description: Convenience functions
    ├── json_extensions.hpp (C++)
    │   └── Description: JSON Path operations Note: We can't modify array elements directly due to clone() semantics JSON Merge operations Copy all fields from base Merge or add fields from overlay Recursive merge for objects Overwrite with overlay value For non-objects, overlay wins JSON Validation Type validation Required fields validation Properties validation
    ├── json_factory.hpp (C++)
    │   └── Description: Forward declaration Factory functions for creating JSON values Builder class for fluent JSON construction Array builder Object builder Add to object Convenience overloads for add Append to array Convenience overloads for append Build the final value Get current value Convenience function to start building Literal operators for JSON values
    ├── json_loader.cpp (C++)
    │   └── Description: JsonLoadException implementation JsonLoader implementation Read entire stream into memory Read from file descriptor Explicit template instantiation for common iterator types Core parsing functions Parse key Parse value Check for duplicate keys Optional minus sign Integer part Leading zero must not be followed by more digits Fractional part Exponent part Optional sign Parse the number Check for overflow/underflow Helper functions Unicode escape sequence Convert to UTF-8 Error handling Validation Convenience functions
    ├── json_loader.hpp (C++)
    │   └── Description: Parse key Parse value Convenience function
    ├── json_packer.cpp (C++)
    │   └── Description: Check for modifiers Process arguments based on format tokens Explicit template instantiations for common types
    ├── json_packer.hpp (C++)
    ├── json_types.cpp (C++)
    │   └── Description: JsonObject implementation JsonArray implementation JsonString implementation JsonNumber implementation JsonBoolean implementation JsonNull implementation
    ├── json_types.hpp (C++)
    │   └── Description: JSON type enumeration Type traits for JSON values
    ├── json_unpacker.cpp (C++)
    │   └── Description: Check for modifiers Process arguments based on format tokens Explicit template instantiations for common types
    ├── json_unpacker.hpp (C++)
    ├── json_value.hpp (C++)
    │   └── Description: Forward declarations Type aliases Base JSON value class Type checking Type casting Serialization Cloning Equality String type Integer type Real number type Remove trailing zeros Boolean type Null type Array type Size and access Modification Iterators Object type Size and access Modification Add a key-value pair to the object Convenience overloads for common types Iterators
    ├── memory.cpp (C++)
    │   └── Description: Fallback to malloc/free emulation
    ├── memory.hpp (C++)
    │   └── Description: Memory resource base class Default memory resource using malloc/free Get the default memory resource Custom memory resource wrapper Fallback to malloc/free emulation Smart pointer for JSON values Factory functions for creating JSON values with specific memory resource This would need to be implemented in the main jansson library For now, we'll just use the regular creation functions Memory resource management
    ├── strbuffer.hpp (C++)
    │   └── Description: Constructor Destructor Copy constructor Move constructor Copy assignment Move assignment Initialize the buffer (for compatibility) Clear the buffer Get the current value as C string Get the current length Get the current capacity Append a single byte Append multiple bytes Pop the last byte Steal the value (transfer ownership) Close/cleanup (for compatibility)
    ├── strconv_wrapper.hpp (C++)
    │   └── Description: C++ wrapper providing compatibility with original C interface These functions can be used as drop-in replacements for jsonp_strtod and jsonp_dtostr Wrapper for jsonp_strtod functionality Converts string buffer to double, returns true on success, false on failure Wrapper for jsonp_dtostr functionality Converts double to string with specified precision Returns the number of characters written, or -1 on error Check if result fits in buffer Copy result to buffer Convenience function using std::string
    ├── string_converter.cpp (C++)
    │   └── Description: Handle exponent sign Find first non-zero digit in exponent If all zeros, keep one zero Remove leading zeros from exponent Add ".0" to distinguish from integer Use classic locale for consistent parsing Check for parsing errors Check for overflow/underflow Set precision and formatting Use fixed notation for small values, scientific for large/small values Normalize the result Check if entire string was consumed Check for negative sign - not allowed for unsigned Check if entire string was consumed Convenience functions
    ├── string_converter.hpp (C++)
    │   └── Description: Convert string to double with locale-independent parsing Convert double to string with locale-independent formatting Convert string to integer Convert integer to string Convert string to unsigned integer Convert unsigned integer to string Use classic locale for consistent parsing/formatting Check if string represents a valid number format Remove leading zeros from exponent part Ensure decimal point or exponent in double string representation Convenience functions for direct usage
    ├── type_traits.hpp (C++)
    ├── utf.cpp (C++)
    │   └── Description: UTF-8 encoding table Lead byte Continuation bytes Check continuation bytes Check for overlong encoding Extract codepoint Check codepoint validity Check for overlong encoding
    └── utf.hpp (C++)
        └── Description: Unicode code point type Validated UTF-8 string class Constructors Getters Iteration Validation Comparison Iterator for UTF-8 code points UTF-8 encoding/decoding functions UTF-8 validation functions UTF-8 iteration Convert string to Utf8String (validates)
├── tests/
    ├── CMakeLists.txt (Text)
    ├── memory_leak_detector.hpp (C++)
    │   └── Description: In a real implementation, you might want to log this For now, we'll just clear the allocations Simple memory leak detection functions
    ├── simple_test.cpp (C++)
    │   └── Description: Setup code if needed Cleanup code if needed Test basic JSON value creation Test array creation Test object creation Test serialization Basic validation of serialized format - check that it contains the expected elements For object, just check that it contains the expected keys and values (order is not guaranteed in JSON objects)
    ├── test_base.hpp (C++)
    │   └── Description: Initialize any common test setup Clean up any common test resources Common test utilities Memory leak detection helper This can be extended with actual memory leak detection For now, it's a placeholder for future implementation JSON validation helper
    ├── test_data_generators.hpp (C++)
    │   └── Description: Generate random JSON objects Generate random JSON arrays Generate random JSON strings Generate random JSON numbers Generate random JSON booleans Generate JSON null Generate test cases for edge cases Generate large JSON objects for performance testing Generate deeply nested JSON for stress testing
    ├── test_main.cpp (C++)
    │   └── Description: Start memory leak monitoring Check for memory leaks Test basic JSON operations Test JSON parsing Test JSON serialization Performance should be reasonable (less than 1 second for 100 properties) Test memory leak detection No leaks should be detected
    └── test_utils.hpp (C++)
        └── Description: Create sample JSON objects Create sample JSON arrays Create sample JSON strings Create sample JSON numbers Create sample JSON booleans Create sample JSON null Compare two JSON values Parse JSON string safely Generate random JSON strings for testing Simple random JSON generator
├── .gitignore (None)
├── README.rst (None)
└── plan.md (Markdown)
└────────────── 
```
