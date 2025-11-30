Data Structure Planning Table

Below is the Data Structure Planning Table and Operation Flow Explanation, applying the concept of a **Browser Navigation System using Dual Stacks** (Back Stack and Forward Stack).


DS-Plan
Operation	Data Structure Used	Reason for Choosing the DS
Visit New Page	Two Stacks (Back & Forward Stacks)	Back Stack stores history, Forward Stack clears when new page is visited
Go Back to Previous Page	Back Stack	LIFO structure allows returning to the most recently visited page
Go Forward	Forward Stack	Stores pages popped from Back stack when user navigates forward
Reload Current Page	Top of Back Stack	Current page is always at the top of Back Stack
Clear History	Both Stacks (Back & Forward)	Easy clearing by emptying both stacks
Operation Flow Explanation
1. Visit New Page
This operation loads a new webpage. When a new URL is opened, the current page is pushed into the **Back Stack**, and the **Forward Stack** is cleared.

Data Structure Used: Two Stacks  
Why Suitable: Dual stack structure perfectly models web browser navigation.  
User Interaction: User types a new URL or clicks a link.
2. Go Back to Previous Page
This operation takes the user to the previous page by popping the top page from the Back Stack and pushing the current page into the Forward Stack.

Data Structure Used: Back Stack  
Why Suitable: LIFO behavior allows returning to the most recent page.  
User Interaction: User clicks the “Back” button.
3. Go Forward
This operation allows the user to go forward to the next page by popping from the Forward Stack and pushing the current page into the Back Stack.

Data Structure Used: Forward Stack  
Why Suitable: Allows reloading previously visited pages in order.  
User Interaction: User clicks the “Forward” button.
