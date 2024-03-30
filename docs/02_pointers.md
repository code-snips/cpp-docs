# Pointers

Understanding pointers and smart pointers is crucial in C++ as they provide powerful tools for memory management and object-oriented programming. This tutorial will introduce both concepts, their usage, differences, and how to effectively apply them in modern C++ development.

## Pointers

Pointers are variables that store the memory address of another variable. They are used for dynamic memory allocation, array management, and implementing data structures and linked lists.

### Basic Pointer Usage

```cpp
#include <iostream>

int main() {
    int var = 10;
    int* ptr = &var;
    
    std::cout << "Value of var: " << var << std::endl;
    std::cout << "Address of var: " << ptr << std::endl;
    std::cout << "Value at address stored in ptr: " << *ptr << std::endl;
}
```

Pointers can be dereferenced using the `*` operator to access or modify the value they point to.

## Smart Pointers

Smart pointers are template classes that ensure automatic memory management to avoid memory leaks. They are part of the C++ Standard Library. The most commonly used smart pointers are `std::unique_ptr`, `std::shared_ptr`, and `std::weak_ptr`.

### `std::unique_ptr`

`std::unique_ptr` owns and manages another object through a pointer and disposes of that object when the `unique_ptr` goes out of scope.

```cpp
#include <iostream>
#include <memory>

int main() {
    std::unique_ptr<int> uniquePtr = std::make_unique<int>(10);
    
    std::cout << "Value of uniquePtr: " << *uniquePtr << std::endl;
}
```

### `std::shared_ptr`

`std::shared_ptr` allows multiple pointers to own the same resource. The resource is freed when the last `shared_ptr` is destroyed.

```cpp
#include <iostream>
#include <memory>

int main() {
    std::shared_ptr<int> sharedPtr1 = std::make_shared<int>(20);
    std::shared_ptr<int> sharedPtr2 = sharedPtr1;
    
    std::cout << "Value of sharedPtr1: " << *sharedPtr1 << std::endl;
    std::cout << "Value of sharedPtr2: " << *sharedPtr2 << std::endl;
    std::cout << "sharedPtr1 use count: " << sharedPtr1.use_count() << std::endl;
}
```

### `std::weak_ptr`

`std::weak_ptr` is a smart pointer that holds a non-owning ("weak") reference to an object that is managed by `std::shared_ptr`. It is used to break cyclic dependencies between `shared_ptr` instances.

```cpp
#include <iostream>
#include <memory>

int main() {
    std::shared_ptr<int> sharedPtr = std::make_shared<int>(30);
    std::weak_ptr<int> weakPtr = sharedPtr;
    
    std::cout << "Value of sharedPtr: " << *sharedPtr << std::endl;
    if (auto tempSharedPtr = weakPtr.lock()) {
        std::cout << "Value of object pointed by weakPtr: " << *tempSharedPtr << std::endl;
    } else {
        std::cout << "The object pointed by weakPtr no longer exists." << std::endl;
    }
}
```