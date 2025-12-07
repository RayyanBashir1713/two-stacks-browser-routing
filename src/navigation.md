#include "navigation.h"
#include <stack>
#include <string>
#include <cstdlib>
#include <iostream>

using namespace std;

void Navigation::visitPage(string url) {
    // Push new page to back stack
    backStack.push(url);

    // Clear forward stack
    while (!forwardStack.empty()) {
        forwardStack.pop();
    }

    // --- Python Module Calls ---
    // Analytics
    string analyticsCmd = "python ..\\python_modules\\analytics.py " + url;
    system(analyticsCmd.c_str());

    // AI Suggestions
    string aiCmd = "python ..\\python_modules\\ai_suggestions.py " + url;
    system(aiCmd.c_str());

    // Phishing Check
    string phishingCmd = "python ..\\python_modules\\phishing.py " + url;
    system(phishingCmd.c_str());
}

string Navigation::goBack() {
    if (backStack.size() <= 1) {
        return "No pages in back history!";
    }

    string topPage = backStack.top();
    backStack.pop();
    forwardStack.push(topPage);

    return backStack.top();
}

string Navigation::goForward() {
    if (forwardStack.empty()) {
        return "No pages in forward history!";
    }

    string page = forwardStack.top();
    forwardStack.pop();
    backStack.push(page);

    return page;
}
