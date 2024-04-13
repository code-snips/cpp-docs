# Parsing

## CPP Deserialization

```cpp
#include <nlohmann/json.hpp>

nlohmann::json j = R"({"name": "John", "age": 30, "is_student": false})"_json;

Person p = j.get<Person>();
```

## CPP Serialization

```cpp
#include <nlohmann/json.hpp>

Person p = {"John", 30, false};
nlohmann::json j = p;

std::cout << j.dump(4) << std::endl;
```

## CPP Customizing Serialization

```cpp
#include <nlohmann/json.hpp>

void to_json(nlohmann::json& j, const Person& p) {
    j = nlohmann::json{{"name", p.name}, {"age", p.age}, {"student_status", p.is_student}};
}

void from_json(const nlohmann::json& j, Person& p) {
    p.name = j.at("name").get<std::string>();
    p.age = j.at("age").get<int>();
    p.is_student = j.at("student_status").get<bool>();
}

```




## Typescript Deserialization

### Using TypeScript Interfaces or Types.

 Defining interfaces or types is a fundamental practice in TypeScript to describe the shape of your objects. This approach allows you to specify the expected structure of the response data at compile-time.

```ts
interface User {
    id: number;
    name: string;
    email: string;
}

axios.get<User>('https://api.example.com/users/1')
    .then(response => {
        const user: User = response.data;
        console.log(user.name);  // TypeScript checks that `name` is a string
    })
    .catch(error => console.error(error));
```

### Generic Axios Functions

```ts
async function fetchData<T>(url: string): Promise<T> {
    const response = await axios.get<T>(url);
    return response.data;
}

// Usage
const userPromise: Promise<User> = fetchData<User>('https://api.example.com/users/1');
```
