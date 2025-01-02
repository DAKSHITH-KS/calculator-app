# calculator-app
first repository on basic calulater
<br>
Author-DAKSHITH K S


/* Firsty we want to import required interface/files
 1..     Java AWT or Abstract Window Toolkit is an API used for developing GUI(Graphic User Interfaces) or Window-Based Applications in Java. Java AWT is part of the Java Foundation Classes (JFC) that provides a way to build platform-independent graphical applications.

 2.. javax.swing. Provides interfaces that enable the development of input methods that can be used with any Java runtime environment.

Java ActionListener is an interface in java. awt. event package. It is an type of class in Java that receives a notification whenever any action is performed in the application. Java ActionListener is alerted whenever the button or menu item is clicked.

Java actionPerformed method is a central aspect of handling event-driven programming concepts. It is part of the ActionListener interface and helps manage user interactions with GUI components.
*/





import javax.swing.*;
import java.awt.*; 
import java.awt.event.*;



public class calculator implements ActionListener{

    calculator(){

    }


public static void main(String[] args) {
        calculator calc = new calculator();
    }



    public void actionPerformed(ActionEvent e){

    }