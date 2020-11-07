# Algebraic-Percentage-Solver
This is a simple algebraic formula made for the convenience finding the percent increase/decrease of what ever two numbers you enter. The idea is to use Java's IntelliJ IDEA program and features to enter in a starting number and a final number and the program is set to do the math for you to find the percentage change between the two. Using the formula, (((final value - starting value) / starting value) * 100) EXAMPLE: If there is an HP laptop at Staples for $759.98 and after 6 months of sitting on the shelf and newer models coming into the store. The manager decided to put a savings tag on it, bringing the new total to $599.99. Your starting value would be the original price, and the final number would be the reduced price. By following this formula the code gives you an accurate percentage, and in this case we would recieve a negative number, indicating that the percent change is a loss of money, the answer being -21.05 percent.


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

package com.Williford;

import java.util.Scanner; // Imports the library and functions for the use of Java's Scanner Tool
public class FindPercent { // This class is simply here to make the code neater, and follows Good Practice
    Scanner Pfinder = new Scanner(System.in); // Allows a unit to use to declare and initialize user input
    double inputA; // Starting Value input Declaration
    double inputB; // Final Value input Declaration

    public void getStartingNumber() { // Method dedicated to asking the user for the starting value, and storing it
        System.out.println("Please enter the starting number:"); // self explanatory
        try { // Begins the try/catch for the below code: Tries the following code, and if invalid, coax to catch
            inputA = Pfinder.nextDouble(); // Creates user input through the above scanners initialization and stores to inputA
        } catch (Exception e) { // catch: Exception, in general catches all exceptions, and follows the below code
            System.out.println("The input you entered is invalid"); // Pre-programmed System message to user
            System.out.println("The error encountered is the \"Exception\"" + e.getMessage()); // programmed message to user
            getStartingNumber();/* the final portion of the catch block is to restart the method to try again if the
             * entry is invalid as to allow for unlimited attempts until it is done correctly, accepts numbers only*/
        } //  <-- this Bracket ends the try catch portion of this method
    } //  <-- This Bracket indicates the end of the getStartingNumber() Method

    public void getFinalNumber() { // Method dedicated to input and retain a number via prompting the user, same as the above method
        System.out.println("Now please enter the final number:"); // Pre-programmed system message prompting for input for final #
        try { // Begins the try/catch functionality for this Method, trying the below code, and catching if input is invalid
            inputB = Pfinder.nextDouble(); // Prompts user for final # input, and stores the variable to inputB via Scanner
        } catch (Exception e) { // Catches any invalid inputs, and forces the below code if exception has occurred
            System.out.println("The input you entered is invalid"); // Pre-programmed System message to user
            System.out.println("The error encountered is the \"Exception\"" + e.getMessage()); /* System message/fetches
            exception message, and displays to user */
            getFinalNumber(); /* Final portion of the catch portion of the try/catch: Reruns getFinalNumber() method and
            allows for unlimited input attempts until the user enters the correct data type, accepts numbers only */
        } // <-- This bracket officially ends the try/catch functionality of this method

    } // <-- This bracket completes,ends, and separates the above getFinalNumber() method

    public void getPercent() { /* This method is created to use the above inputs (inputA, inputB) to run the formula
        to give the user the percentage, it is the final step of this program. */
        double percentage = ( ( ( inputB - inputA ) / inputA ) * 100 ); /* Declares, and Initializes a new double to obtain
            the change in percent */
        try { // Begins the try catch for the code below
            System.out.printf("%.2f percent", ( percentage )); /* Instead of using the textbook System.out.print or .println,
            "printf" allows for the use of format functions from the Printstream Java library, if you would like to
            see more than just 2 numbers after the decimal point for the percentage return, change the 2 to a higher #
            If you would like to just round up or down, you could consider changing the printf, to print, or println and
            use the math.floor(), or math.Ceiling(). */
        } catch (Exception e) { // catches any invalid input and returns the below code
            System.out.println(percentage + "%"); /* if there is a problem with printf accepting the input, catch:
                will force the input to be run as a println, the above methods have there own try/catches so the inputs
                to this point are guaranteed to be valid numbers, so if the printf malfunctions the catch will force it to
                return your answer regardless, minus the isolation of 2 numbers after the decimal point, you will recieve
                the entire decimal return. */
        }

    } // <-- This bracket officially ends the getPercent() method above.


} // <-- This bracket is the end of the public FindPercent class
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

package com.Williford;

public class Main { // This is the main class, this class holds the main method that runs the program

    public static void main(String[] args) { // Standard main method
        FindPercent a = new FindPercent(); // Creates a link to the FindPercent() class to access its contents
        /*System.out.println("To find the percentage on either increase or decrease between two numbers");
        System.out.println("You must first enter the starting number, and the final number, and this system");
        System.out.println("Will do the rest of the work for you.");*/

        /* The above Greyed out area can be used if you delete the "/*" symbol above, it simply explains what the
        program does, what it expects, and what it wants from you as a user, directions basically, I greyed it out as a
        comment for fast usage of the program itself. */

        a.getStartingNumber(); /* a is name of the link created to access the FindPercent contents, and runs the
        following methods since it is under the main method: First is the getStartingNumber() Method */
        a.getFinalNumber(); // Calls the 2nd part of the program, after the first method is finished: getFinalNumber()
        //System.out.println("If you entered your numbers in correctly then this result is 100% correct");

        /* The above comment is a system message I greyed out to allow for quick usage, if you want it to be displayed
        all you need to do is delete the "//" before the "System.out.println()". */

        System.out.println("The result of what you entered is\n"); // Pre-programmed System message

        a.getPercent();/* Once the above methods have been completed, this is the final piece of code to be accessed,
        by using the link to the FindPercent class like the above, it runs the newly stored variables, and runs the
        formula for the percent change, and then displays it to the user. */
    } // <-- This bracket ends the main method
} // <-- This bracket ends the Main class

/* I hope you enjoy this piece of code, I developed it for its simplicity, and ease of use for those of you out there
who need to find the percent change within a problem. If you are at all code savvy you can easily adjust some of the code
to allow for different uses, and more complex formulas for further math assistance.

Best Wishes,

-Tony
 */
