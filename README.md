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
<br>


import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class calculator implements ActionListener{

    // jpanel
    JFrame frame;
    JTextField textfield;
    JButton[] numberButtons = new JButton[10];
    JButton[] functionButtons = new JButton[9];
    JButton addButton,subButton,mulButton,divButton;
    JButton decButton, equButton, delButton, clrButton,negButton;
    JPanel panel;

    Font myFont = new Font("Ink Free",Font.BOLD,30);

    double num1=0, num2=0,result =0;
    char operator;

    // contrator
    calculator(){

        frame = new JFrame("calculator");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(420,550);
        frame.setLayout(null);

        textfield = new JTextField();
        textfield.setBounds(50,25,300,50);
        textfield.setFont(myFont);
        textfield.setEditable(false);

        addButton = new JButton("+");
        subButton = new JButton("-");
        mulButton = new JButton("*");
        divButton = new JButton("/");

        negButton = new JButton("(-)");
        decButton = new JButton(".");
        clrButton = new JButton("CLEAR");
        equButton = new JButton("=");
        delButton = new JButton("Delete");
        
        functionButtons[0] = addButton;
        functionButtons[1] = subButton;
        functionButtons[2] = mulButton;
        functionButtons[3] = divButton;
        functionButtons[4] = decButton;
        functionButtons[5] = equButton;
        functionButtons[6] = delButton;
        functionButtons[7] = clrButton;
        functionButtons[8] = negButton;
        
        for(int i=0;i<9;i++){
            functionButtons[i].addActionListener(this);
            functionButtons[i].setFont(myFont);
            functionButtons[i].setFocusable(false);
        }

        for(int i=0;i<10;i++){
            numberButtons[i]= new JButton(String.valueOf(i));
            numberButtons[i].addActionListener(this);
            numberButtons[i].setFont(myFont);
            numberButtons[i].setFocusable(false);
        }


        negButton.setBounds(50,430,100,50);
        delButton.setBounds(150,430,100,50);
        clrButton.setBounds(250,430,100,50);
        

        panel = new JPanel(); 
        panel.setBounds(50,100,300,300);
        panel.setLayout(new GridLayout(4,4,10,10));
        panel.setBackground(Color.black);

        panel.add(numberButtons[1]);
        panel.add(numberButtons[2]);
        panel.add(numberButtons[3]);
        panel.add(addButton);
        panel.add(numberButtons[4]);
        panel.add(numberButtons[5]);
        panel.add(numberButtons[6]);
        panel.add(subButton);
        panel.add(numberButtons[7]);
        panel.add(numberButtons[8]);
        panel.add(numberButtons[9]);
        panel.add(mulButton);
        panel.add(decButton);
        panel.add(numberButtons[0]);
        panel.add(equButton);
        panel.add(divButton);

        frame.add(panel);
        frame.add(negButton);
        frame.add(delButton);
        frame.add(clrButton);
        frame.add(textfield);
        frame.setVisible(true);
    


    }



    public static void main(String[] args) {
        calculator calc = new calculator();
    }



    public void actionPerformed(ActionEvent e){

        for(int i=0;i<10;i++){
            if(e.getSource()== numberButtons[i]){
                textfield.setText(textfield.getText().concat(String.valueOf(i)));
            }
        }
        if(e.getSource()==decButton){
            textfield.setText(textfield.getText().concat("."));
        }
        if(e.getSource()==addButton){
            num1 = Double.parseDouble(textfield.getText());
            operator ='+';
            textfield.setText("");
        }
        if(e.getSource()==subButton){
            num1 = Double.parseDouble(textfield.getText());
            operator ='-';
            textfield.setText("");
        }
        if(e.getSource()==mulButton){
            num1 = Double.parseDouble(textfield.getText());
            operator ='*';
            textfield.setText("");
        }
        if(e.getSource()==divButton){
            num1 = Double.parseDouble(textfield.getText());
            operator ='/';
            textfield.setText("");
    
        }
        if(e.getSource()==equButton){
            num2=Double.parseDouble(textfield.getText());

            switch (operator) {
                case'+':
                    result=num1+num2;
                    break;
                case'-':
                    result=num1-num2;
                    break;
                case'*':
                    result=num1*num2;
                    break;
                case'/':
                    result=num1/num2;
                    break;
            }
            textfield.setText(String.valueOf(result));
            num1=result;
        }
        if(e.getSource()==clrButton){
            textfield.setText("");
        }
    if(e.getSource()==delButton){
        String string = textfield.getText();
        textfield.setText("");
        for(int i=0;i<string.length()-1;i++){
            textfield.setText(textfield.getText()+string.charAt(i));
        }
    }
        if(e.getSource()==negButton){
            double temp = Double.parseDouble(textfield.getText());
            temp *=-1;
            textfield.setText(String.valueOf(temp));
            }
    }
}