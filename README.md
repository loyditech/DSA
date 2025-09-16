#include <iostream>
#include <string>

using namespace std;

const int MAX_LIST = 150;

struct Student {
    string srcode;
    string full_name;
    string section;
    string program;
    string time_in;
    string time_out;
};

Student students[MAX_LIST];
int student_count = 0;

void create_student(){
   if (student_count < MAX_LIST) {
      cout << "Enter student Srcode: ";
      cin >> students[student_count].srcode;
      cout << "Enter student full name: ";
      cin.ignore();
      getline(cin, students[student_count].full_name);
        cout << "Enter section: ";
        getline(cin, students[student_count].section);
        cout << "Enter program: ";
        getline(cin, students[student_count].program);
        cout << "Enter time in: ";
        getline(cin, students[student_count].time_in);
        cout << "Enter time out: ";
        getline(cin, students[student_count].time_out);
        student_count++;
        cout << "Student record created successfully!" << endl;
    } else {
        cout << "Student list is full." << endl;
    }
}
void list_student (){
    if (student_count == 0) {
      cout << "No student list found" << endl;
    }else{
        for (int i = 0; i < student_count; i++) {
            cout << "Srcode:" << students[i].srcode << ", Full name: " << students[i].full_name
            << " , Section:" << students[i].section << ", Program: " << students[i].program
            << ", Time in:" << students[i].time_in << ", Time out: " << students[i].time_out << endl;
        }
    }
       
}
void main_menu() {
    while (true) {
        cout << "\nLibrary Management System" << endl;
        cout << "1. Create Student Record" << endl;
        cout << "2. List of Student " << endl;
        cout << "3. Update Student Record" << endl;
        cout << "4. Delete Student Record" << endl;
        cout << "5. Exit" << endl;
        cout << "Enter your choice: ";
        int choice;
        cin >> choice;

        switch (choice) {
            case 1:
                create_student();
                break;
            case 2:
                list_student();
                break;
            case 3:
                
                break;
            case 4:
          
                break;
            case 5:
                cout << "Exiting the program. Goodbye!" << endl;
                return;
            default:
                cout << "Invalid choice. Please try again." << endl;
        }
    }
}

int main () {
    main_menu();
    return 0;
}
   











