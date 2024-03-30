# Concurrency

Concurrency in C++ is a powerful feature that allows your program to run multiple operations in parallel, making better use of the available hardware resources. This tutorial covers the basics of concurrency, threading, the use of mutexes for synchronization, and ensuring thread safety in modern C++.

## Threading

Threading is the most fundamental aspect of concurrency. C++11 introduced the `<thread>` library, simplifying the creation and management of threads.

### Creating Threads

To create a thread, you instantiate an object of `std::thread` and pass a function to run in parallel.

```cpp
#include <iostream>
#include <thread>

void helloWorld() {
    std::cout << "Hello, World from a thread!" << std::endl;
}

int main() {
    std::thread t(helloWorld);
    t.join(); // Wait for the thread to finish
}
```

### Passing Arguments to Threads

Arguments can be passed to the thread function directly.

```cpp
#include <iostream>
#include <thread>

void printMessage(const std::string& message) {
    std::cout << message << std::endl;
}

int main() {
    std::thread t(printMessage, "Hello from the thread with arguments!");
    t.join();
}
```

## Mutex for Synchronization

When multiple threads access shared resources, data races and inconsistencies can occur. Mutexes are used to synchronize access to shared resources, ensuring thread safety.

### Using Mutex

Here's how you can use a mutex to synchronize access to a shared variable.

```cpp
#include <iostream>
#include <thread>
#include <mutex>

std::mutex mtx;
int sharedVariable = 0;

void incrementSharedVariable() {
    mtx.lock();
    ++sharedVariable;
    mtx.unlock();
}

int main() {
    std::thread t1(incrementSharedVariable);
    std::thread t2(incrementSharedVariable);
    
    t1.join();
    t2.join();
    
    std::cout << "Shared Variable: " << sharedVariable << std::endl;
}
```

### std::lock_guard

`std::lock_guard` is a mutex wrapper that provides a convenient RAII-style mechanism for owning a mutex for the duration of a scoped block.

```cpp
#include <iostream>
#include <thread>
#include <mutex>

std::mutex mtx;
int sharedVariable = 0;

void safeIncrement() {
    std::lock_guard<std::mutex> guard(mtx);
    ++sharedVariable;
}

int main() {
    std::thread t1(safeIncrement);
    std::thread t2(safeIncrement);
    
    t1.join();
    t2.join();
    
    std::cout << "Shared Variable: " << sharedVariable << std::endl;
}
```

## Thread Safety

Thread safety is a concept in concurrency that ensures that shared data is accessed by multiple threads without causing data corruption or inconsistencies.

### Strategies for Thread Safety

- **Mutexes**: As shown above, mutexes can protect shared data.
- **Atomic Types**: C++ provides atomic types in the `<atomic>` header, which can be used without the need for explicit mutexes for simple data types.
- **Thread-Local Data**: Data that is only accessed by a single thread does not need synchronization.
- **Immutable Data**: Data that does not change after its creation does not require synchronization.
