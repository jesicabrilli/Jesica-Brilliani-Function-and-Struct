#include <iostream>
#include <iomanip>
#include <string>
using namespace std;

const int NUM_STUDENTS = 20;
const int NUM_TESTS = 3;

struct studentType {
    string studentFName;
    string studentLName;
    int testScore[NUM_TESTS];
    char grade;
};

// Fungsi untuk membaca data siswa
void readData(studentType students[]) {
    string firstNames[NUM_STUDENTS] = {
        "Luna", "Yessa", "Angga", "Lisa", "Azer", "Chayara", "Saskia", "Ahsan", "Cheryl", "Dina",
        "Sonic", "Anggel", "Anitya", "Nella", "Ceysa", "Nadia", "Nixon", "Renata", "Salsa", "Reyhan"
    };
    string lastNames[NUM_STUDENTS] = {
        "Fadila", "Muhamad", "Prasetya", "Gelia", "Alima", "Gotik", "Halim", "Brilliani", "Puspita", "Abiyu",
        "Ardiwan", "Decanti", "Kusita", "Silahoho", "Pratiwi", "Kandela", "Qusuma", "Adelav", "Munandiya", "Firdaus"
    };

    int sampleScores[NUM_STUDENTS][NUM_TESTS] = {
        {85, 90, 88}, {78, 82, 80}, {92, 95, 94}, {60, 65, 70}, {88, 84, 86},
        {75, 70, 72}, {90, 93, 91}, {68, 70, 69}, {95, 96, 97}, {80, 85, 83},
        {77, 79, 78}, {89, 87, 90}, {93, 92, 91}, {66, 64, 68}, {82, 85, 84},
        {79, 81, 80}, {94, 96, 95}, {73, 75, 74}, {86, 88, 87}, {91, 90, 92}
    };

    for (int i = 0; i < NUM_STUDENTS; ++i) {
        students[i].studentFName = firstNames[i];
        students[i].studentLName = lastNames[i];
        for (int j = 0; j < NUM_TESTS; ++j) {
            students[i].testScore[j] = sampleScores[i][j];
        }
    }
}

// Fungsi untuk menentukan grade
void assignGrade(studentType students[]) {
    for (int i = 0; i < NUM_STUDENTS; ++i) {
        int total = 0;
        for (int j = 0; j < NUM_TESTS; ++j) {
            total += students[i].testScore[j];
        }
        int avg = total / NUM_TESTS;

        if (avg >= 90) students[i].grade = 'A';
        else if (avg >= 80) students[i].grade = 'B';
        else if (avg >= 70) students[i].grade = 'C';
        else if (avg >= 60) students[i].grade = 'D';
        else students[i].grade = 'F';
    }
}

// Fungsi untuk mencari skor tertinggi
int findHighestScore(studentType students[]) {
    int highest = 0;
    for (int i = 0; i < NUM_STUDENTS; ++i) {
        for (int j = 0; j < NUM_TESTS; ++j) {
            if (students[i].testScore[j] > highest)
                highest = students[i].testScore[j];
        }
    }
    return highest;
}

// Fungsi untuk mencetak siswa dengan skor tertinggi
void printTopScorers(studentType students[], int highest) {
    cout << "\nStudents with the highest test score (" << highest << "):\n";
    for (int i = 0; i < NUM_STUDENTS; ++i) {
        for (int j = 0; j < NUM_TESTS; ++j) {
            if (students[i].testScore[j] == highest) {
                cout << left << setw(15) << (students[i].studentLName + ", " + students[i].studentFName) << endl;
                break;
            }
        }
    }
}

// Fungsi untuk mencetak semua data siswa
void printAllStudents(studentType students[]) {
    cout << left << setw(25) << "Name" << "Scores\t\tGrade\n";
    cout << "-----------------------------------------------\n";
    for (int i = 0; i < NUM_STUDENTS; ++i) {
        cout << left << setw(25) << (students[i].studentLName + ", " + students[i].studentFName);
        for (int j = 0; j < NUM_TESTS; ++j) {
            cout << students[i].testScore[j] << " ";
        }
        cout << "\t" << students[i].grade << endl;
    }
}

int main() {
    studentType students[NUM_STUDENTS];

    readData(students);
    assignGrade(students);
    int highest = findHighestScore(students);

    printAllStudents(students);
    printTopScorers(students, highest);

    return 0;
}
