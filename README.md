import java.util.Scanner;
class Calculator
{
    float a,b;
    private String operation;
    public Calculator(float a, float b, String operation) 
    {
        this.a = a;
        this.b = b;
        this.operation = operation.toLowerCase();
    }
    public String calculate()
    {
        switch (operation)
        {
            case "add":
                return String.valueOf(a + b);
            case "subtract":
                return String.valueOf(a - b);
            case "multiply":
                return String.valueOf(a * b);
            case "divide":
                if (b != 0) 
                {
                    return String.valueOf(a / b);
                } 
                else
                {
                    return "Error: Division by zero";
                }
            default:
                return "Error: Invalid operation";
        }
    }
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Enter the first number (a): ");
        double a = scanner.nextDouble();
        System.out.println("Enter the second number (b): ");
        double b = scanner.nextDouble();
        System.out.println("Enter the type of operation (add, subtract, multiply, divide): ");
        String operation = scanner.next();
        Calculator calculator = new Calculator(a, b, operation);
        String result = calculator.calculate();
        System.out.println("Result: " + result);
        scanner.close();
    }
}
