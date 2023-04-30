#include <iostream>
#include <string>
#include <fstream>
#include <istream>
#include <stdlib.h>
#include <time.h>
#include <cstdio>
#include <math.h>
#include <cmath>
#include <sstream>
#include <forward_list>
#include <algorithm>
#include <list>
#include <vector>
#include <array>
#include <string>
#include <deque>
#include <stdexcept>
#include <windows.h>

using namespace std;

class Employee
{
public:
    Employee(string name, string score, int age) {
        Name = name;
        Jobtitle = score;
        salary = age;
    }
    string getName() const {
        return Name;
    }

    string getJobTitle() const {
        return Jobtitle;
    }

    int getSalary() const {
        return salary;
    }

    string Name;
    string Jobtitle;
    int salary;

private:
};

class Statics {
public:
    auto Or() {
        vector<Employee> people{
             Employee("Вася", "Директор", 23000),
             Employee("Петя", "Зам. Д.", 21000),
             Employee("Маша", "Бухгалтер", 10000),
             Employee("Катя", "Менеджер", 12000)
        };
        int i = 0;
        for (const auto& person : people) {
            i++;
            cout << i << " - " << person.Name << endl;
        }
        cout << "Какой из пользователей вас заинтересовал?\n: ";
        cin >> ChoiseInt;
        switch (ChoiseInt) {
        case 1:
            cout << "Name: " << people[0].getName() << "\tJob title: " << people[0].getJobTitle() << "\tSalary: " << people[0].getSalary() << endl;
            break;
        case 2:
            cout << "Name: " << people[1].getName() << "\tJob title: " << people[1].getJobTitle() << "\tSalary: " << people[1].getSalary() << endl;
            break;
        case 3:
            cout << "Name: " << people[2].getName() << "\tJob title: " << people[2].getJobTitle() << "\tSalary: " << people[2].getSalary() << endl;
            break;
        case 4:
            cout << "Name: " << people[3].getName() << "\tJob title: " << people[3].getJobTitle() << "\tSalary: " << people[3].getSalary() << endl;
            break;
        }

        cout << "====================================================================" << endl;
        for (const auto& person : people) {
            cout << "Name: " << person.getName() << "\tJob title: " << person.getJobTitle() << "\tSalary: " << person.getSalary() << endl;
        }
    }
private:
    int ChoiseInt;
};

int main() {
    setlocale(LC_ALL, "");
    Statics Statics;
    Statics.Or();
    return 0;
}
