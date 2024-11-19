# C-sharp-Operator Overloading
1.
using System;
public class Program
{
    public static void Main(string[] args)
    {
        // Creating two Point objects
        Point point1 = new Point(3, 4);
        Point point2 = new Point(5, 6);
        
        // Adding the points using the overloaded + operator
        Point result = point1 + point2;
        
        // Displaying the result
        result.Display(); // Output: (8, 10)
    }
}

2.
using System;
public class ComplexNumber

{
 public int Real; 
 public int Imaginary;
 public ComplexNumber(int real, int imaginary)
{
 Real = real;
 Imaginary = imaginary;
}
// Overloading + operator
  public static ComplexNumber operator +(ComplexNumber c1, ComplexNumber c2)

{
// Adds real parts and imaginary parts
  return new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary);
}
  public void Display()
{

Console.WriteLine($"{Real} + {Imaginary}i");
}

}


3.using System;

public class Number
{
    public int Value;

    public Number(int value)
    {
        Value = value;
    }

    // Overloading - operator to subtract two Number objects
    public static Number operator -(Number n1, Number n2)
    {
        return new Number(n1.Value - n2.Value);
    }

    // Overloading * operator to multiply two Number objects
    public static Number operator *(Number n1, Number n2)
    {
        return new Number(n1.Value * n2.Value);
    }

    // Overloading / operator to divide two Number objects
    public static Number operator /(Number n1, Number n2)
    {
        if (n2.Value == 0)
            throw new DivideByZeroException("Cannot divide by zero!");
        return new Number(n1.Value / n2.Value);
    }

    public void Display()
    {
        Console.WriteLine($"Value: {Value}");
    }
}

class Program
{
    static void Main()
    {
        Number num1 = new Number(20);
        Number num2 = new Number(5);

        // Using overloaded - operator
        Number resultSubtraction = num1 - num2;
        resultSubtraction.Display(); // Output: Value: 15

        // Using overloaded * operator
        Number resultMultiplication = num1 * num2;
        resultMultiplication.Display(); // Output: Value: 100

        // Using overloaded / operator
        Number resultDivision = num1 / num2;
        resultDivision.Display(); // Output: Value: 4
    }
}


