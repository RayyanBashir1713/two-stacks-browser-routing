#ifndef NAVIGATION_H
#define NAVIGATION_H

#include <stack>
#include <string>
using namespace std;

class Navigation {
private:
    stack<string> backStack;
    stack<string> forwardStack;

public:
    void visitPage(string url);
    string goBack();
    string goForward();
};

#endif
