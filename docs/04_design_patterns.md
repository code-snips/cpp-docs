# Patterns

Design Patterns for C++
 - [Patterns Refacotring Guru](https://refactoring.guru/design-patterns/cpp)
 - [YT](https://www.youtube.com/watch?v=0mcP8ZpUR38&list=PL9fI-Wx9MOtNlnYL6LjKqrUOhd5Xg0t1O&index=1&t=27s)
 - [Github](https://github.com/ArjanCodes/2021-composition-vs-inheritance)

 Prefer composition to reduce coupling. 

 Use 1-layer abstarct classes for the components. this way you also enable dependency injection

 See Example 
 ```
 employee = Emplyee(Person, Contract, Commission)

 ```

 The Contract for example is an abstract class, concrete implementations are: HourlyContract, SalariedContract, FreelancerContract