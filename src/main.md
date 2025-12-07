#include <iostream>
#include <string>
#include "navigation.h"

using namespace std;

int main() {
    Navigation nav;
    string url;
    int choice;

    cout << "==== Futuristic Browser Navigation System ====\n";

    while (true) {
        cout << "\nMenu:\n";
        cout << "1. Visit New Page\n";
        cout << "2. Go Back\n";
        cout << "3. Go Forward\n";
        cout << "4. Exit\n";
        cout << "Enter choice: ";
        cin >> choice;

        if (choice == 1) {
            cout << "Enter URL: ";
            cin >> url;

            nav.visitPage(url);  // Python calls automatically from navigation.cpp
            cout << "Visited: " << url << endl;

        } else if (choice == 2) {
            cout << "Back to: " << nav.goBack() << endl;

        } else if (choice == 3) {
            cout << "Forward to: " << nav.goForward() << endl;

        } else if (choice == 4) {
            cout << "Exiting Browser Navigation System.\n";
            break;

        } else {
            cout << "Invalid choice! Try again.\n";
        }
    }

    return 0;
}
