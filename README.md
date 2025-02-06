# calculator-app
first repository on basic calulater
<br>
Author-DAKSHITH K S

/* Firsty we want to import required interface/files
<br>
 1..     Java AWT or Abstract Window Toolkit is an API used for developing GUI(Graphic User Interfaces) or Window-Based Applications in Java. Java AWT is part of the Java Foundation Classes (JFC) that provides a way to build platform-independent graphical applications.
<br>
 2.. javax.swing. Provides interfaces that enable the development of input methods that can be used with any Java runtime environment.
<br>
Java ActionListener is an interface in java. awt. event package. It is an type of class in Java that receives a notification whenever any action is performed in the application. Java ActionListener is alerted whenever the button or menu item is clicked.
<br>
Java actionPerformed method is a central aspect of handling event-driven programming concepts. It is part of the ActionListener interface and helps manage user interactions with GUI components.
<br>
<br>
The actionPerformed method is used to define behaviors for each button click:
Number Buttons: Appends the clicked number to the JTextField content using concat.
<br>
Decimal Button: Appends a decimal point to the current text.
<br>
Operator Buttons: Captures the first number (num1) and the operator, then clears the JTextField for the second input.
<br>
Equals Button: •	Captures the second number (num2) and performs the operation based on the captured operator (+, -, *, /) using a switch statement.
	•	The result is displayed in the JTextField, and num1 is updated to allow chaining operations.
<br>
Clear Button:
	•	Clears the JTextField to reset the input.
<br>
Delete Button:
	•	Removes the last character from the current input text using a loop.
<br>
Negative Button:
	•	Converts the current number to its negative or positive equivalent by multiplying it by -1.
<br>
Panel Arrangement:
	•	Number buttons (0-9) and basic arithmetic operators (+, -, *, /) are added to the grid-based JPanel.
	•	Additional buttons like “CLEAR,” “Delete,” and “(-)” are positioned outside the panel for easy accessibility.
    .   to this we can add the color to the panel and also we want to assign the height and width of the pannel layout and boundry
<br>
<br>
Buttons Setup:
	•	All buttons are initialized, styled with the same font for consistency, and added to the appropriate arrays (numberButtons and functionButtons), arithmetic operations (+, -, *, /), additional features (decimal, negate), and utility functions (delete, clear, and equals). 
	•	Action listeners are added to each button to handle clicks.
<br>
<br>
JFrame: Serves as the main application window. It is titled “calculator” and set to a fixed size of 420x550 pixels.
	•	JTextField: Used for input and output display. It is set to be non-editable (setEditable(false)) to prevent user modifications outside button clicks.
*/
<br>

