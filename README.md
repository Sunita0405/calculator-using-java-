import java.util.Scanner;

public class calculator {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        try {
            System.out.print("Enter first number: ");
            double num1 = sc.nextDouble(); //nextDouble() reads a decimal (or integer) number.

            System.out.print("Enter second number: ");
            double num2 = sc.nextDouble();

            System.out.println("\nChoose an operation:");
            System.out.println("+  Addition");
            System.out.println("-  Subtraction");
            System.out.println("*  Multiplication");
            System.out.println("/  Division");
            System.out.print("Enter operator: ");

            char op = sc.next().charAt(0); //next() reads the next input as a string.charAt(0) takes the first character.

            double result; //A variable to store the answer.

            switch (op) { //Checks the value of op → Java looks at the value stored in the variable op.Executes the matching case → It compares op with each case label and runs the code for the matching one.
                case '+':
                    result = num1 + num2;
                    System.out.println("Result = " + result);
                    break;

                case '-':
                    result = num1 - num2;
                    System.out.println("Result = " + result);
                    break;

                case '*':
                    result = num1 * num2;
                    System.out.println("Result = " + result);
                    break;

                case '/':
                    if (num2 == 0) {
                        throw new ArithmeticException("Cannot divide by zero.");
                    }
                    result = num1 / num2;
                    System.out.println("Result = " + result);
                    break;

                default:
                    System.out.println("Invalid Operator!");
            }

        } catch (ArithmeticException e) {
            System.out.println("Error: " + e.getMessage());

        } catch (Exception e) {
            System.out.println("Invalid Input!");

        } finally {
            System.out.println("Calculator Closed.");
            sc.close();
        }
    }
}
