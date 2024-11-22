# BT1
using System;
using System.Collections.Generic;
using System.Linq;

class Student
{
    public int Id { get; set; }
    public string Name { get; set; }
    public int Age { get; set; }
}

class Program
{
    static void Main(string[] args)
    {
        // TAO DSHS
        List<Student> students = new List<Student>
        {
            new Student { Id = 1, Name = "An", Age = 16 },
            new Student { Id = 2, Name = "Binh", Age = 14 },
            new Student { Id = 3, Name = "Anh", Age = 17 },
            new Student { Id = 4, Name = "Cuong", Age = 15 },
            new Student { Id = 5, Name = "Dung", Age = 18 }
        };

        // a.IN DS TOAN BO HS
        Console.WriteLine("DS TOAN BO HS:");
        foreach (var student in students)
        {
            Console.WriteLine($"ID: {student.Id}, Name: {student.Name}, Age: {student.Age}");
        }

        // b. TIM HS CO TUOI TU 15-18
        Console.WriteLine("\nHS CO TUOI TU 15-18");
        var ageFilter = students.Where(s => s.Age >= 15 && s.Age <= 18);
        foreach (var student in ageFilter)
        {
            Console.WriteLine($"ID: {student.Id}, Name: {student.Name}, Age: {student.Age}");
        }

        // c. TIM HS CO TEN BAT DAU BANG CHU "A"
        Console.WriteLine("\nHS CO TEN BAT DAU BANG CHU \"A\" ");
        var nameFilter = students.Where(s => s.Name.StartsWith("A"));
        foreach (var student in nameFilter)
        {
            Console.WriteLine($"ID: {student.Id}, Name: {student.Name}, Age: {student.Age}");
        }

        // d. TINH TONG SO TUOI HS
        int totalAge = students.Sum(s => s.Age);
        Console.WriteLine($"\nTONG SO TUOI HS: {totalAge}");

        // e. TIM HS CO TUOI LON NHAT
        int maxAge = students.Max(s => s.Age);
        var oldestStudent = students.First(s => s.Age == maxAge);
        Console.WriteLine($"\nHS CO TUOI LON NHAT: ID: {oldestStudent.Id}, Name: {oldestStudent.Name}, Age: {oldestStudent.Age}");

        // f. SAP SEP HS THEO TUOI TANG DAN 
        Console.WriteLine("\nSAP SEP HS THEO TUOI TANG DAN :");
        var sortedStudents = students.OrderBy(s => s.Age);
        foreach (var student in sortedStudents)
        {
            Console.WriteLine($"ID: {student.Id}, Name: {student.Name}, Age: {student.Age}");
        }
    }
}
