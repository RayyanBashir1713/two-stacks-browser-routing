Pseudocode - Browser Navigation System Using Dual Stacks
Initializing Browser
FUNCTION InitializeBrowser()
    CREATE EMPTY STACK BackStack
    CREATE EMPTY STACK ForwardStack
    SET CurrentPage ← "Home"
END FUNCTION
Visiting Page
FUNCTION VisitPage(NewPage)
    PUSH CurrentPage INTO BackStack
    CLEAR ForwardStack
    SET CurrentPage ← NewPage
END FUNCTION
Go back
FUNCTION GoBack()
    IF BackStack IS EMPTY THEN
        DISPLAY "No previous page."
    ELSE
        PUSH CurrentPage INTO ForwardStack
        SET CurrentPage ← POP FROM BackStack
    END IF
END FUNCTION
Go forward
FUNCTION GoForward()
    IF ForwardStack IS EMPTY THEN
        DISPLAY "No forward page."
    ELSE
        PUSH CurrentPage INTO BackStack
        SET CurrentPage ← POP FROM ForwardStack
    END IF
END FUNCTION
Show Current Page
FUNCTION ShowCurrentPage()
    DISPLAY "You are currently on: " + CurrentPage
END FUNCTION
