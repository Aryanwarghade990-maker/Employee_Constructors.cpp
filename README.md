# Employee_Constructors.cpp
#include <iostream>
#include <string>
using namespace std;

class Employee {
private:
    int empId;
    string name;
    float basicSalary;
    float bonus;
    float totalSalary;

public:
    // Default constructor
    Employee() {
        empId = 0;
        name = "Unknown";
        basicSalary = 0;
        bonus = 0;
        totalSalary = 0;
    }

    // Parameterized constructor
    Employee(int id, string n, float salary, float b) {
        empId = id;
        name = n;
        basicSalary = salary;
        bonus = b;
        calculateTotalSalary();
    }

    void calculateTotalSalary() {
        totalSalary = basicSalary + bonus;
    }

    void display() {
        cout << "Employee ID: " << empId << endl;
        cout << "Name: " << name << endl;
        cout << "Basic Salary: " << basicSalary << endl;
        cout << "Bonus: " << bonus << endl;
        cout << "Total Salary: " << totalSalary << endl;
    }
};

int main() {
    // Using default constructor
    Employee emp1;
    cout << "Default Constructor - Employee 1:" << endl;
    emp1.display();
    
    cout << "\n-------------------------" << endl;
    
    // Using parameterized constructor
    Employee emp2(101, "John Doe", 50000, 10000);
    cout << "Parameterized Constructor - Employee 2:" << endl;
    emp2.display();
    
    cout << "\n-------------------------" << endl;
    
    // Taking input for parameterized constructor
    int id;
    string name;
    float salary, bonus;
    cout << "Enter Employee ID: ";
    cin >> id;
    cin.ignore();
    cout << "Enter Name: ";
    getline(cin, name);
    cout << "Enter Basic Salary: ";
    cin >> salary;
    cout << "Enter Bonus: ";
    cin >> bonus;
    
    Employee emp3(id, name, salary, bonus);
    cout << "\nEmployee 3 Details:" << endl;
    emp3.display();
    
    return 0;
}
