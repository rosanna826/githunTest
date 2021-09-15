import java.awt.FlowLayout;
import java.awt.Color;
import java.awt.Dimension;
import java.awt.Container;
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JPanel;
import javax.swing.JTextField;
import javax.swing.SwingUtilities;
import java.awt.event.ActionListener;
import java.awt.event.ActionEvent;
import javafx.scene.input.KeyEvent;
import java.awt.Font;

//import java.awt.GridLayout;
import java.util.Scanner;

/**
 * Write a description of class TextGUIDemo here.
 *
 * @author (RY)
 * @version (24.08.2021)
 */
public class TextGUIDemo extends JFrame implements ActionListener {
    JPanel glassPanel;

    //for the buttons 
    private JButton btn0;
    private JButton btn1;
    private JButton btn2;
    private JButton btn3;
    private JButton btn4;
    private JButton btn5;
    private JButton btn6;
    private JButton btn7;
    private JButton btn8;
    private JButton btn9;
    private JButton btn10; // +/-
    private JButton btn11; // .
    private JButton btn12; // +
    private JButton btn13; // -
    private JButton btn14; // *
    private JButton btn15; // /
    private JButton btn16; // !
    private JButton btn17; // <<
    private JButton btn18; // C
    private JButton btn19; // (
    private JButton btn20; // )
    private JButton btn21; // OFF
    private JButton btn22; // = 

    JTextField textField;
    //display
    private String expression = "";
    private double first_number;
    private double second_number;
    //private char operator;
    private double result;
    private char sign = '+';

    /**
     * Constructor for objects of class TextGUIDemo
     */
    public TextGUIDemo()
    {
        super ("        My PROG5001 - Calculator (version)  ");
        setLayout(null);
        // create panels
        JFrame frame = new JFrame();
        glassPanel = new JPanel();
        glassPanel.setLayout(null);
        glassPanel.setBackground(Color.white);
        glassPanel.setSize(380,480);
        glassPanel.setLocation(10,10);
        //GridLayout layout = new GridLayout(0,5);
        //layout.setHgap(10);
        //layout.setVgap(10);
        //
        add(glassPanel);

        //left = width, right = hight
        btn1 = new JButton("1");
        btn1.setSize(50,50);
        btn1.setLocation(10,80);    
        btn2 = new JButton("2");
        btn2.setSize(50,50);
        btn2.setLocation(70,80);
        btn3 = new JButton("3");
        btn3.setSize(50,50);
        btn3.setLocation(130,80);
        btn12 = new JButton("+");
        btn12.setSize(50,50);
        btn12.setLocation(190,80);
        btn17 = new JButton("<<"); //BACKSPACE
        btn17.setSize(80,50);
        btn17.setLocation(250,80);
        btn1.setBackground(Color.lightGray);
        btn2.setBackground(Color.lightGray);  
        btn3.setBackground(Color.lightGray);
        btn12.setBackground(Color.lightGray);
        btn17.setBackground(Color.lightGray);

        btn4 = new JButton("4");
        btn4.setSize(50,50);
        btn4.setLocation(10,150);
        btn5 = new JButton("5");
        btn5.setSize(50,50);
        btn5.setLocation(70,150);
        btn6 = new JButton("6");
        btn6.setSize(50,50);
        btn6.setLocation(130,150);
        btn13 = new JButton("-");
        btn13.setSize(50,50);
        btn13.setLocation(190,150);
        btn18 = new JButton("C"); //CLEAR
        btn18.setSize(80,50);
        btn18.setLocation(250,150);
        btn4.setBackground(Color.lightGray);
        btn5.setBackground(Color.lightGray);
        btn6.setBackground(Color.lightGray);
        btn13.setBackground(Color.lightGray);
        btn18.setBackground(Color.lightGray);

        btn7 = new JButton("7");
        btn7.setSize(50,50);
        btn7.setLocation(10,220);
        btn8 = new JButton("8");
        btn8.setSize(50,50);
        btn8.setLocation(70,220);
        btn9 = new JButton("9");
        btn9.setSize(50,50);
        btn9.setLocation(130,220);
        btn14 = new JButton("*");
        btn14.setSize(50,50);
        btn14.setLocation(190,220);
        btn19 = new JButton("(");
        btn19.setSize(80,50);
        btn19.setLocation(250,220);
        btn7.setBackground(Color.lightGray);
        btn8.setBackground(Color.lightGray);
        btn9.setBackground(Color.lightGray);
        btn14.setBackground(Color.lightGray);
        btn19.setBackground(Color.lightGray);

        btn10 = new JButton("+/-");
        btn10.setSize(50,50);
        btn10.setLocation(10,280);
        btn10.setBackground(Color.lightGray);
        btn0 = new JButton("0");
        btn0.setSize(50,50);
        btn0.setLocation(70,280);
        btn0.setBackground(Color.lightGray);
        btn11 = new JButton(" . ");
        btn11.setSize(50,50);
        btn11.setLocation(130,280);
        btn11.setBackground(Color.lightGray);
        btn15 = new JButton("/");
        btn15.setSize(50,50);
        btn15.setLocation(190,280);
        btn15.setBackground(Color.lightGray);
        btn20 = new JButton(")");
        btn20.setSize(80,50);
        btn20.setLocation(250,280);
        btn20.setBackground(Color.lightGray);

        btn22 = new JButton("=");
        btn22.setSize(170,50);
        btn22.setLocation(10,340);
        btn22.setBackground(Color.lightGray);
        btn16 = new JButton("!");
        btn16.setSize(50,50);
        btn16.setLocation(190,340); 
        btn16.setBackground(Color.lightGray);
        btn21= new JButton("OFF"); //EXIT
        btn21.setSize(80,50);
        btn21.setLocation(250,340);
        btn21.setBackground(Color.orange);

        // add buttons back to the panel
        glassPanel.add(btn0);
        glassPanel.add(btn1);
        glassPanel.add(btn2);
        glassPanel.add(btn3);
        glassPanel.add(btn4);
        glassPanel.add(btn5);
        glassPanel.add(btn6);
        glassPanel.add(btn7);
        glassPanel.add(btn8);
        glassPanel.add(btn9);
        glassPanel.add(btn10);
        glassPanel.add(btn11);
        glassPanel.add(btn12);
        glassPanel.add(btn13);
        glassPanel.add(btn14);
        glassPanel.add(btn15);
        glassPanel.add(btn16);
        glassPanel.add(btn17);
        glassPanel.add(btn18);
        glassPanel.add(btn19);
        glassPanel.add(btn20);
        glassPanel.add(btn21);
        glassPanel.add(btn22);

        //ActionListener
        btn0.addActionListener(this);
        btn0.setActionCommand("btnzero");
        btn1.addActionListener(this);
        btn1.setActionCommand("btnone");
        btn2.addActionListener(this);
        btn2.setActionCommand("btntwo");
        btn3.addActionListener(this);
        btn3.setActionCommand("btnthree");
        btn4.addActionListener(this);
        btn4.setActionCommand("btnfour");
        btn5.addActionListener(this);
        btn5.setActionCommand("btnfive");
        btn6.addActionListener(this);
        btn6.setActionCommand("btnsix");
        btn7.addActionListener(this);
        btn7.setActionCommand("btnseven");
        btn8.addActionListener(this);
        btn8.setActionCommand("btneight");
        btn9.addActionListener(this);
        btn9.setActionCommand("btnnine");
        btn10.addActionListener(this);
        btn10.setActionCommand("btnten");        
        btn11.addActionListener(this);
        btn11.setActionCommand("btneleven");
        btn12.addActionListener(this);
        btn12.setActionCommand("btntwelve");
        btn13.addActionListener(this);
        btn13.setActionCommand("btnthirteen");
        btn14.addActionListener(this);
        btn14.setActionCommand("btnfourteen");
        btn15.addActionListener(this);
        btn15.setActionCommand("btnfifteen");
        btn16.addActionListener(this);
        btn16.setActionCommand("btnsixteen");
        btn17.addActionListener(this);
        btn17.setActionCommand("btnseventeen");
        btn18.addActionListener(this);
        btn18.setActionCommand("btneighteen");
        btn19.addActionListener(this);
        btn19.setActionCommand("btnnineteen");
        btn20.addActionListener(this);
        btn20.setActionCommand("btntwenty");
        btn21.addActionListener(this);
        btn21.setActionCommand("btntwentyone");
        btn22.addActionListener(this);
        btn22.setActionCommand("btntwentytwo");

        //display
        textField = new JTextField();
        textField.setSize(320,60);
        textField.setLocation(20,20);
        Font displayFont = new Font("New Roman",Font.BOLD,20);
        textField.setFont(displayFont);
        add(textField);
        //textField.KeyListener(this);

        // initialise instance vatiables
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        setCursor(CROSSHAIR_CURSOR);
        setPreferredSize(new Dimension (400,500));
        pack();

        //setFocusable(this);
        //addKeyListener(this);
    }

    public void actionPerformed(ActionEvent e) {
        String cmd = e.getActionCommand();
        if (cmd ==("btnone")) { 
            if (sign =='-'){
            expression = expression + "-1";
            //sign = '+';
        } else
            expression = expression + "1";

        }else 
        if (cmd==("btntwo")) {
            if (sign =='-'){
            expression = expression + "-2";
            //sign = '+';
             } else
            expression = expression + "2";
        } else 
        if (cmd==("btnthree")) {
            if (sign =='-'){
            expression = expression + "-3";
            //sign = '+';
             } else
            expression = expression + "3";
        } else 
        if (cmd==("btnfour")) {
            if (sign =='-'){
            expression = expression + "-4";
            //sign = '+';
             } else
            expression = expression + "4";
        } else 
        if (cmd==("btnfive")) {
            if (sign =='-'){
            expression = expression + "-5";
            //sign = '+';
             } else
            expression = expression + "5";
        } else 
        if (cmd==("btnsix")) {
            if (sign =='-'){
            expression = expression + "-6";
            //sign = '+';
             } else
            expression = expression + "6";
        } else 
        if (cmd==("btnseven")) {
            if (sign =='-'){
            expression = expression + "-7";
            //sign = '+';
             } else
            expression = expression + "7";
        } else 
        if (cmd==("btneight")) {
            if (sign =='-'){
            expression = expression + "-8";
            //sign = '+';
             } else
            expression = expression + "8";
        } else 
        if (cmd==("btnnine")) {
            if (sign =='-'){
            expression = expression + "-9";
            //sign = '+';
             } else
            expression = expression + "9";
        } else 
        if (cmd==("btnzero")) {
            expression = expression + "0";
        } else 
        if (cmd==("btnten")) { //+/-
            if (sign=='+'){
                sign = '-';
            }else 
                 sign = '+';
            //double ops;
            // ops = expression * (-1);
            //expression = String.valueOf(ops);
        } else 
        if (cmd==("btneleven")) {
            expression = expression + ".";
        } else 
        if (cmd==("btntwelve")) {
            expression = expression + " " + "+" + " ";
            //operator = '+';
        } else 
        if (cmd==("btnthirteen")) {
            expression = expression + " " + "-" + " ";
            //operator = '-';
        } else 
        if (cmd==("btnfourteen")) {
            expression = expression + " " + "*" + " ";
            // operator = '*';
        } else 
        if (cmd==("btnfifteen")) {
            expression = expression +  " " + "/" + " ";
            //operator = '/';
        } else 
        if (cmd==("btnsixteen")) {

            expression = expression + " !" ;
            //long factorial = 1;
            //int number;
            //for (int counter = number; counter >=2;counter--)
            //factorial = factorial * counter;
        } else 
        if (cmd==("btnseventeen")) {
            //Button for "Backspace"
            int len = expression.length();
            expression = expression.substring(0,len-1);
        } else 
        if (cmd==("btneighteen")) {
            //Button for "Clear"
            expression = "";
        } else 
        if (cmd==("btnnineteen")) {
            expression = expression + "(";
        } else 
        if (cmd==("btntwenty")) {
            expression = expression + ")";
        } else 
        if (cmd==("btntwentyone")) {
            //button for "OFF";
            System.exit(0);
        } else 
        if (cmd==("btntwentytwo")) { //=
            ReadOpearator();
            //result = factorial();
            expression = "=" + " " + String.valueOf(result);
        }
        textField.setText(expression);
    }

    /**
     * An method to read in operator from the user
     * 
     * @param
     * @return  the operator
     */
    public void ReadOpearator() {
        String operator;
        boolean invalid;
        byte count = 0;
        do {
            Scanner inScanner = new Scanner (expression);
            first_number  = inScanner.nextDouble();
            operator= inScanner.next();
            second_number = inScanner.nextDouble();
            invalid = false;
            if (operator.equals ("+")) {
                //operator = '+';
                //ReadArguments();
                addition();
                invalid = true;
            } else
            if (operator.equals ("-")){
                //operator = '-';
                //ReadArguments();
                subtraction();
                invalid = true;
            } else
            if (operator.equals ("*")){
                //operator = '*';
                //ReadArguments();
                multiplication(); 
                invalid = true;
            } else
            if (operator.equals ("/")){
                //operator = '/';
                //ReadArguments();
                division(); 
                invalid = true;
            }

        } while (invalid == false);

    }

    /**
     * An method to perform addition operation
     */
    public double addition() {
        //perform the clculation
        //double result;
        result = first_number + second_number;
        expression = expression + result;
        return result;

    }

    /**
     * An method to perform a subtraction operation
     */
    public double subtraction() {
        //perform the calculation
        //double result;
        result = first_number - second_number;
        expression = expression + result;
        return result;
    }

    /**
     * An method to perform division operation
     */
    public double division() {
        //perform the calculation
        //double result;
        result = first_number / second_number;
        expression = expression + result;
        return result;
    }

    /**
     * An method to perform multiplication operation
     */
    public double multiplication() {
        //perform the calculation
        //double result;
        result = first_number * second_number;
        expression = expression + result;
        return result;
    }

    /**
     * An method to perform factorial operation
     */
    public double factorial() {
        int number;
        long factorial = 1;
        String operator;
        boolean invalid;
        
        Scanner inScanner = new Scanner (expression);
        number  = inScanner.nextInt();
        operator= inScanner.next();
  
            if (operator.equals ("!")) {
                for (int i =1; i<= number; i++) {
                    factorial = factorial * i;
        
                }
            }
        return number;

    }

    
    public static void main (String[] args ) {
        TextGUIDemo frame = new TextGUIDemo();
        frame.setVisible(true);
    }
}
