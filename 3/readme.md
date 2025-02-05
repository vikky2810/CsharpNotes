
# C# DLL Creation and Usage Example

This repository demonstrates the creation and usage of a Dynamic Link Library (DLL) in C#. The practical task is to develop a DLL file and use it in an application program.

## Project Overview

The project consists of two parts:
1. **DLL Project**: A class library that contains reusable methods.
2. **Console Application**: An application that references the DLL and uses its methods.

## Folder Structure

```
/MyLibrary       - Contains the class library (DLL)
    /MyLibrary.csproj
    /Class1.cs
/MyApp           - Console Application that references the DLL
    /MyApp.csproj
    /Program.cs
README.md        - Project documentation (this file)
```

## How to Use

### Step 1: Create the DLL

1. **Open Visual Studio** and create a new **Class Library** project. Name it `MyLibrary`.
2. **Write the Code**:
   In `Class1.cs`, add the following methods:

   ```csharp
   public class MyLibraryClass
   {
       public string GetMessage()
       {
           return "Hello from the DLL!";
       }

       public int AddNumbers(int a, int b)
       {
           return a + b;
       }
   }
   ```

3. **Build the DLL**:
   - Right-click the **MyLibrary** project in the **Solution Explorer** and click **Build**.
   - This will generate a `MyLibrary.dll` in the `bin\Debug` or `bin\Release` folder.

### Step 2: Create the Console Application

1. **Create a New Console App** project and name it `MyApp`.
2. **Add the DLL as a Reference**:
   - Right-click on **References** in the **Solution Explorer** of the console app.
   - Choose **Add Reference** and browse to the `MyLibrary.dll` file you just built.
3. **Write the Code**:
   In `Program.cs`, use the following code to call the methods from the DLL:

   ```csharp
   using System;
   using MyLibrary;  // Namespace of your DLL

   class Program
   {
       static void Main(string[] args)
       {
           // Create an object of the class from the DLL
           MyLibraryClass myLibrary = new MyLibraryClass();

           // Call the methods from the DLL
           Console.WriteLine(myLibrary.GetMessage());
           Console.WriteLine("Sum: " + myLibrary.AddNumbers(5, 7));
       }
   }
   ```

### Step 3: Run the Application

1. **Run the Application**:
   - Press **Ctrl + F5** or **F5** to execute the console application.
   - The output should display:

   ```
   Hello from the DLL!
   Sum: 12
   ```

## Conclusion

This project shows how to create a DLL in C# and reference it in a console application. This is a simple example but can be extended to more complex use cases where you need to share common functionality across multiple projects.

