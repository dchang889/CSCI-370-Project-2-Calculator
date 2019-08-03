# CSCI-370-Project-2-Calculator

Group project to create a GUI for a four-function calculator
Daniel Chang
Dennis Chang
Ka Leung
Jason Polanco
Junkai Zhang

Mission Statement
•	To implement a GUI for a four-function calculator.
Demo Test
•	The demo test was successful. A series of tests were conducted on the calculator involving various sequences of keys being clicked. Some of the tests conducted included tests for leading zeroes, trailing zeroes, and for division by zero. The checks and catches ran effectively and were able to trap the various possibilities a user may enter onto a calculator.
Bugs Discovered in the Demo
•	No bugs were discovered in the demo.
Debugging Procedures and Tests to Check the Functionality
•	Entering multiple zeroes to check for leading zeroes.
o	If the display is “0”, do not concatenate “0” onto display
•	Computing for answers that are decimals to check for trailing zeroes and decimal format
o	Java’s Decimal Format eliminates trailing zeroes and entering “.” and “4” results in “0.4”, not “.4”
•	Negative Zero
o	If the display is “0”, do not concatenate “-” onto display
•	Divide by Zero
o	If second operand is “0”, display “error”
•	After Divide by Zero attempt, String “error” in display is causing errors
o	Background: After correcting the Divide by Zero bug, the user will run into errors if he or she tries to continue using the calculator. Numbers become concatenated to the string “error” while operations and “=” make attempts to do math with a String variable.
o	Code is implemented to treat the “error” like the initial “0” on start up so that the user may continue using the calculator instead of having to restart. (The user may also click “A/C” or “C” but the additional checks saves the user this step)
•	Computational errors from clicking operation buttons consecutively
o	Background: Initially, the display would be “0” before the user enters an input as an operand. Clicking an operation button would have the value in the display taken in as the first operand (by design, this ensures that the last two operands would be used). If a user entered “6+-2”, the calculator computed it as if the user entered “6+0-2”. (We want the user to have the flexibility of changing operations)
o	Display is cleared after every operation button is clicked. The second to last input is preserved as the first operand. 
•	Large and small numbers
o	Use scientific notation as the format for displaying results
o	Limitations: Numbers can only be as extreme as a double variable may hold
•	Results can be concatenated (This should not be)
o	Add a Boolean to check if the number in the display is a result so that it cannot be concatenated 
•	Dangling Negative
o	Add a check in the delete method where if a dangling negative exists, set display to “0”
•	Negative Zeroes and their “Equivalents”
o	If result were to display negative zero or its “equivalent”, set display to “0”
Additional Software Checks and Tests to Validate Functionality
•	Calculator was tested on multiple platforms and the GUI was found to be too small on some screens
o	Font size increased keep the calculator relatively large 
•	Click “0” to test for trailing zeroes
•	Click “.” at various points to verify if decimal points appeared when it should not
o	For “error”
o	For numbers represented in scientific notation
•	Click “+/-” to see if the sign value toggles and when it should not toggle
o	On positive or negative numbers
o	On decimals
o	On numbers represented in scientific notation
o	On error
o	And whether the computations involving use of the “+/-“ are valid
•	Click “Del” on the first and/or second operand to verify functionality
•	Click “C” at various points to verify if the most recent operand was cleared.
o	While entering the first operand
o	While entering the second operand
•	Click “A/C” at any point to verify if all operands were cleared.

Note: Many bug fixes would often resolve issues with other bugs or result in more bugs.
