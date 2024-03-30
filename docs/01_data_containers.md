# Containers

In modern C++, beyond the primitive data types, there are several advanced data types that facilitate complex data management and operations. Among these, vectors, sets, and structs are extensively used. This tutorial provides an overview of these types, demonstrating their utility and application.

## Vectors

Vectors are part of the Standard Template Library (STL) and represent a sequence of elements that can grow dynamically. Unlike arrays, vectors can adjust their size automatically.

### Basic Usage of Vectors

```cpp
#include <vector>

int main() {
    std::vector<int> numbers = {1, 2, 3, 4, 5};
    numbers.push_back(6); // Adds a new element at the end
    numbers.pop_back(); // Removes the last element
}
```

Vectors are versatile, supporting random access, insertion, and deletion of elements.

## Sets

Sets are a collection of unique elements, sorted by their values. They are useful for operations like union, intersection, and difference.

### Basic Usage of Sets

```cpp
#include <set>

int main() {
    std::set<int> uniqueNumbers = {2, 4, 2, 1, 3};
    uniqueNumbers.insert(5); // Adds a new element
    uniqueNumbers.erase(1); // Removes an element
}
```

Sets automatically remove duplicates and keep elements sorted.

## Structs

Structs are user-defined data types that group variables under a single name. They are useful for creating complex data structures that represent objects or concepts.

### Defining and Using a Struct

```cpp
#include <string>

struct Person {
    std::string name;
    int age;
};

int main() {
    Person person = {"John Doe", 30};
}
```

Structs provide a way to model data more closely to real-world entities, making code more readable and maintainable.
