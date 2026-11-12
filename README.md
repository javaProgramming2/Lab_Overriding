# Lab_Overriding
This project asks the user if they are a full-time employee or a part-time employee, then uses if-statements to run blocks of code which both create an object to use modified methods in order to calculate the monthly salary of the user, depending on whether the user is a full-time employee or a part-time employee.
``` java
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 */

package com.mycompany.lab_overriding;

/**
 *
 * @author Stefan
 */
import java.util.Scanner;
public class Lab_Overriding
{
    public static void main(String[] args)
    {
        Scanner keyboard = new Scanner(System.in);
        System.out.print("Enter employee type (Full-time/Part-time): ");
        if (keyboard.nextLine().equalsIgnoreCase("Full-time"))
        {
            FullTimeEmployee emp = new FullTimeEmployee();
            System.out.print("Enter base pay: $");
            emp.basePay = keyboard.nextDouble();
            System.out.print("Enter bonus: $");
            emp.bonus = keyboard.nextDouble();
            System.out.println("Monthly Salary: $" + emp.calculateSalary());
        }
        if (keyboard.nextLine().equalsIgnoreCase("Part-time"))
        {
            PartTimeEmployee emp = new PartTimeEmployee();
            System.out.print("Enter hourly pay: $");
            emp.hourlyRate = keyboard.nextDouble();
            System.out.print("Enter hours worked: ");
            emp.hoursWorked = keyboard.nextDouble();
            System.out.println("Monthly Salary: $" + emp.calculateSalary());
        }
    }
}
class Employee
{
    double calculateSalary()
    {
        return 0.0;
    }
}
class FullTimeEmployee extends Employee
{
    double basePay;
    double bonus;
    @Override
    double calculateSalary()
    {
        return basePay + bonus;
    }
}
class PartTimeEmployee extends Employee
{
    double hourlyRate;
    double hoursWorked;
    @Override
    double calculateSalary()
    {
        return hourlyRate * hoursWorked;
    }
}
```
