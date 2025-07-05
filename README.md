# CodeAlfa_Task
#include <iostream>
#include <vector>
#include <iomanip>
using namespace std;

int main() {
    int numCourses;
    cout << "Enter number of courses: ";
    cin >> numCourses;

    vector<double> grades(numCourses);
    vector<int> credits(numCourses);

    double totalGradePoints = 0;
    int totalCredits = 0;

    for (int i = 0; i < numCourses; i++) {
        cout << "\nEnter grade for course " << i + 1 << ": ";
        cin >> grades[i];

        cout << "Enter credit hours for course " << i + 1 << ": ";
        cin >> credits[i];

        totalGradePoints += grades[i] * credits[i];
        totalCredits += credits[i];
    }

    double cgpa = totalGradePoints / totalCredits;

    // Display results
    cout << "\n--- Course Summary ---\n";
    cout << left << setw(10) << "Course" << setw(10) << "Grade" << setw(15) << "Credit Hours" << endl;
    for (int i = 0; i < numCourses; i++) {
        cout << left << setw(10) << (i + 1) << setw(10) << grades[i] << setw(15) << credits[i] << endl;
    }

    cout << "\nTotal Credits: " << totalCredits;
    cout << "\nTotal Grade Points: " << totalGradePoints;
    cout << fixed << setprecision(2);
    cout << "\nYour CGPA is: " << cgpa << endl;

    return 0;
}
