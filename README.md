1. Create an abstract class Vehicle with abstract method fuelEfficiency().
Derive classes Car and Bike to override this method. Demonstrate
constructor chaining and runtime polymorphism.

Code:
using System;
abstract class Vehicle
{
    protected string Brand;

    public Vehicle(string brand)
    {
        Brand = brand;
        Console.WriteLine("Vehicle constructor called");
    }
    public abstract void FuelEfficiency();
}
class Car : Vehicle
{
    public Car(string brand) : base(brand)
    {
        Console.WriteLine("Car constructor called");
    }

    public override void FuelEfficiency()
    {
        Console.WriteLine($"{Brand} Car fuel efficiency: 15 km/l");
    }
}
class Bike : Vehicle
{
    public Bike(string brand) : base(brand)
    {
        Console.WriteLine("Bike constructor called");
    }
    public override void FuelEfficiency()
    {
        Console.WriteLine($"{Brand} Bike fuel efficiency: 40 km/l");
    }
}
class Program
{
    static void Main()
    {
        Vehicle v1 = new Car("Toyota");
        Vehicle v2 = new Bike("Yamaha");
        v1.FuelEfficiency();
        v2.FuelEfficiency();
    }
}
Output:  <img width="468" height="222" alt="image" src="https://github.com/user-attachments/assets/aa45c5ec-5cef-4b59-b61d-8a9a4fb35e68" />

 
2. Create an abstract class Employee with an abstract method
calculateSalary(). Derive classes Manager and Developer. Implement
overriding and constructor chaining to calculate salaries differently.

Code:
using System;
abstract class Employee
{
    protected string Name;
    protected double BaseSalary;
    public Employee(string name, double baseSalary)
    {
        Name = name;
        BaseSalary = baseSalary;
        Console.WriteLine("Employee constructor called");
    }
    public abstract void CalculateSalary();
}
class Manager : Employee
{
    public Manager(string name, double baseSalary) : base(name, baseSalary)
    {
        Console.WriteLine("Manager constructor called");
    }
    public override void CalculateSalary()
    {
        double total = BaseSalary + 10000;
        Console.WriteLine($"Manager {Name} Salary: {total}");
    }
}
class Developer : Employee
{
    public Developer(string name, double baseSalary) : base(name, baseSalary)
    {
        Console.WriteLine("Developer constructor called");
    }
    public override void CalculateSalary()
    {
        double total = BaseSalary + 5000;
        Console.WriteLine($"Developer {Name} Salary: {total}");
    }
}
class Program
{
    static void Main()
    {
        Employee e1 = new Manager("Kashish", 40000);
        Employee e2 = new Developer("Dharmi", 35000);
        e1.CalculateSalary();
        e2.CalculateSalary();
    }
}
Output:  <img width="431" height="232" alt="image" src="https://github.com/user-attachments/assets/54c7ad8f-5f1f-49dc-93a6-732f512f04f6" />

 
3. Create a base class Shape and derived classes Rectangle and Circle.
Implement method overriding to calculate the area of the respective
shapes. Include constructor chaining and use of abstract class.

Code:
using System;
abstract class Shape
{
    public abstract double CalculateArea();
}
class Rectangle : Shape
{
    double Length, Breadth;
    public Rectangle(double l, double b)
    {
        Length = l;
        Breadth = b;
        Console.WriteLine("Rectangle constructor called");
    }
    public override double CalculateArea()
    {
        return Length * Breadth;
    }
}
class Circle : Shape
{
    double Radius;
    public Circle(double r)
    {
        Radius = r;
        Console.WriteLine("Circle constructor called");
    }
    public override double CalculateArea()
    {
        return 3.14 * Radius * Radius;
    }
}
class Program
{
    static void Main()
    {
        Shape s1 = new Rectangle(5, 3);
        Shape s2 = new Circle(4);
        Console.WriteLine("Area of Rectangle: " + s1.CalculateArea());
        Console.WriteLine("Area of Circle: " + s2.CalculateArea());
    }
}
Output:  <img width="522" height="184" alt="image" src="https://github.com/user-attachments/assets/0c4be7c9-c3ec-41d3-889f-1314d5136148" />

 

4. Create an abstract class Payment with abstract method processPayment().
Derive classes CreditCardPayment and UPIPayment. Implement overriding
and constructor chaining.

Code:
using System;
abstract class Payment
{
    protected double Amount;

    public Payment(double amount)
    {
        Amount = amount;
        Console.WriteLine("Payment constructor called");
    }
    public abstract void ProcessPayment();
}
class CreditCardPayment : Payment
{
    public CreditCardPayment(double amount) : base(amount)
    {
        Console.WriteLine("Credit Card Payment constructor called");
    }
    public override void ProcessPayment()
    {
        Console.WriteLine($"Credit Card Payment of Rs.{Amount} processed successfully!");
    }
}
class UPIPayment : Payment
{
    public UPIPayment(double amount) : base(amount)
    {
        Console.WriteLine("UPI Payment constructor called");
    }
    public override void ProcessPayment()
    {
        Console.WriteLine($"UPI Payment of Rs.{Amount} processed successfully!");
    }
}
class Program
{
    static void Main()
    {
        Payment p1 = new CreditCardPayment(1500);
        Payment p2 = new UPIPayment(800);
        p1.ProcessPayment();
        p2.ProcessPayment();
    }
}
Output:  <img width="818" height="270" alt="image" src="https://github.com/user-attachments/assets/2686fb7d-1ec9-4b4e-bd97-9bae35e1ffdc" />

 

5. Create an abstract class Temperature with abstract method
convert().Derive classes Celsius and Fahrenheit.Implement convert() to
convert Celsius ↔ Fahrenheit.


Code:
using System;
abstract class Temperature
{
    public abstract void Convert(double value);
}
class Celsius : Temperature
{
    public override void Convert(double value)
    {
        double fahrenheit = (value * 9 / 5) + 32;
        Console.WriteLine($"{value}°C = {fahrenheit}°F");
    }
}
class Fahrenheit : Temperature
{
    public override void Convert(double value)
    {
        double celsius = (value - 32) * 5 / 9;
        Console.WriteLine($"{value}°F = {celsius}°C");
    }
}
class Program
{
    static void Main()
    {
        Temperature t1 = new Celsius();
        Temperature t2 = new Fahrenheit();
        t1.Convert(25);   // Celsius to Fahrenheit
        t2.Convert(98);   // Fahrenheit to Celsius
    }
}
Output:  <img width="480" height="109" alt="image" src="https://github.com/user-attachments/assets/a73f9430-1f90-4873-ab7d-8b1ba8ffa2b9" />

 

