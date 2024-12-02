#include <iostream>​

using namespace std;​

​

// Function to convert letter grades to numeric values​

double letterToNumeric(char grade) {​

    if (grade == 'A' || grade == 'a') return 4.0;​

    if (grade == 'B' || grade == 'b') return 3.0;​

    if (grade == 'C' || grade == 'c') return 2.0;​

    if (grade == 'D' || grade == 'd') return 1.0;​

    if (grade == 'F' || grade == 'f') return 0.0;​

    cout << "Invalid grade entered. Assuming grade is F.\n";​

    return 0.0;​

}​

​

// Function to calculate GPA​

double calculateGPA(double grades[], double credits[], int numCourses) {​

    double totalPoints = 0, totalCredits = 0;​

    for (int i = 0; i < numCourses; i++) {​

        totalPoints += grades[i] * credits[i];​

        totalCredits += credits[i];​

    }​

    return (totalCredits == 0) ? 0 : totalPoints / totalCredits;​

}​

​

int main() {​

    int numCourses;​

    cout << "Welcome to GPA Calculator!" << endl;​

    cout << "Enter the number of courses: ";​

    cin >> numCourses;​

​

    double grades[100], credits[100];​

    for (int i = 0; i < numCourses; i++) {​

        char letterGrade;​

        cout << "Course " << i + 1 << " letter grade (A-F): ";​

        cin >> letterGrade;​

        grades[i] = letterToNumeric(letterGrade);​

​

        cout << "Credit hours for this course: ";​

        cin >> credits[i];​

    }​

​

    double gpa = calculateGPA(grades, credits, numCourses);​

    cout << "Your GPA is: " << gpa << endl;​

​

    if (gpa >= 3.5) cout << "Great job! You're doing excellent!" << endl;​

    else if (gpa >= 2.0) cout << "Keep it up! You're on track." << endl;​

    else cout << "Don't give up! Work harder next time." << endl;​

​

    return 0;​

}​

​
