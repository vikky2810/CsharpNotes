# OOP Concepts in C# - Class, Inheritance, and Extension Methods

## 📌 Overview
This project demonstrates **Object-Oriented Programming (OOP) concepts in C#**, including:
- **Class (Encapsulation)**
- **Implementation Inheritance**
- **Extension Methods**

A simple **Employee Management System** is used as an example.

## 📌 Concepts Covered
### ✅ 1. Class (Encapsulation)
A `class` is a blueprint for creating objects. The `Employee` class includes properties, a constructor, and a method.

```csharp
using System;

class Employee
{
    // Properties (Encapsulation)
    public string Name { get; set; }
    public int Age { get; set; }
    public double Salary { get; set; }

    // Constructor
    public Employee(string name, int age, double salary)
    {
        Name = name;
        Age = age;
        Salary = salary;
    }

    // Method
    public void DisplayInfo()
    {
        Console.WriteLine($"Name: {Name}, Age: {Age}, Salary: {Salary:C}");
    }
}
```

### ✅ 2. Inheritance (Implementation Inheritance)
The `Manager` class **inherits** from `Employee` and adds a `Bonus` property.

```csharp
class Manager : Employee
{
    public double Bonus { get; set; }

    // Constructor using base class
    public Manager(string name, int age, double salary, double bonus)
        : base(name, age, salary)
    {
        Bonus = bonus;
    }

    // Overriding method
    public void DisplayManagerInfo()
    {
        Console.WriteLine($"Manager: {Name}, Age: {Age}, Salary: {Salary:C}, Bonus: {Bonus:C}");
    }
}
```

### ✅ 3. Extension Methods
An **extension method** adds a method to an existing class **without modifying it**.

```csharp
static class EmployeeExtensions
{
    public static double GetTotalSalary(this Manager manager)
    {
        return manager.Salary + manager.Bonus;
    }
}
```

### ✅ 4. Main Program
The `Main` method demonstrates object creation and method usage.

```csharp
class Program
{
    static void Main()
    {
        // Creating an Employee object
        Employee emp = new Employee("John Doe", 30, 50000);
        emp.DisplayInfo();

        // Creating a Manager object (Inheritance)
        Manager mgr = new Manager("Alice Smith", 40, 80000, 20000);
        mgr.DisplayManagerInfo();

        // Using Extension Method
        Console.WriteLine($"Total Salary of {mgr.Name}: {mgr.GetTotalSalary():C}");
    }
}
```

### ✅ 5. Output
```
Name: John Doe, Age: 30, Salary: $50,000.00
Manager: Alice Smith, Age: 40, Salary: $80,000.00, Bonus: $20,000.00
Total Salary of Alice Smith: $100,000.00
```

## 📌 How to Run the Code
1. Open a **C# compiler** (e.g., Visual Studio, Visual Studio Code, or an online C# compiler).
2. Copy and paste the code into a new C# console application.
3. Run the program to see the output.

## 📌 Next Steps
- Implement **Encapsulation** using private fields and getters/setters.
- Add **Polymorphism** by overriding methods.
- Use **Interfaces** to introduce multiple inheritance.

