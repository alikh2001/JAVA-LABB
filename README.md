//Q:1:
public class MatrixAddition {
 public static void main(String[] args) {
 if (args.length != 1) {
 System.out.println("Usage: java MatrixAddition N");
 System.exit(1);
 }
 int N = Integer.parseInt(args[0]);
 if (N <= 0) {
 System.out.println("N must be a positive integer.");
 System.exit(1);
 }
 int[][] matrixA = new int[N][N];
 int[][] matrixB = new int[N][N];
 int[][] result = new int[N][N];
 // Fill matrixA and matrixB with values (you can modify this part)
 fillMatrix(matrixA, N);
 fillMatrix(matrixB, N);
 // Add the matrices
 addMatrices(matrixA, matrixB, result, N);
 // Display the matrices
 System.out.println("Matrix A:");
 printMatrix(matrixA);
 System.out.println("Matrix B:");
 printMatrix(matrixB);
 System.out.println("Result of Matrix Addition:");
 printMatrix(result);
 }
 // Fill a matrix with random values (you can modify this part)
 public static void fillMatrix(int[][] matrix, int N) {
 for (int i = 0; i < N; i++) {
 for (int j = 0; j < N; j++) {
 matrix[i][j] = i + j; // You can change this to your desired values
 }
 }
  }
 // Add two matrices
 public static void addMatrices(int[][] A, int[][] B, int[][] result, int N) {
 for (int i = 0; i < N; i++) {
 for (int j = 0; j < N; j++) {
 result[i][j] = A[i][j] + B[i][j];
 }
 }
 }
 // Print a matrix
 public static void printMatrix(int[][] matrix) {
 for (int[] row : matrix) {
 for (int value : row) {
 System.out.print(value + " ");
 }
 System.out.println();
 }
 }
}

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
//Q:2)
class Stack {
 private int maxSize = 10;
 private int top;
 private int[] stackArray;
 public Stack() {
 stackArray = new int[maxSize];
 top = -1; // Initialize the top of the stack
 }
 public void push(int item) {
 if (top < maxSize - 1) {
 stackArray[++top] = item;
 System.out.println("Pushed: " + item);
 } else {
 System.out.println("Stack is full. Cannot push " + item);
 }
 }
 public int pop() {
 if (top >= 0) {
 int item = stackArray[top--];
 System.out.println("Popped: " + item);
 return item;
 } else {
 System.out.println("Stack is empty. Cannot pop.");
 return -1; // Indicate an empty stack
 }
 }
 public void display() {
 System.out.print("Stack: ");
 for (int i = 0; i <= top; i++) {
 System.out.print(stackArray[i] + " ");
 }
 System.out.println();
 }
}
public class StackExample {
 public static void main(String[] args) {
 Stack stack = new Stack();
 stack.push(5);
 stack.push(10);
 stack.push(15);
 stack.display();
 int poppedItem = stack.pop();
 if (poppedItem != -1) {
 System.out.println("Popped item: " + poppedItem);
 }
 stack.display();
 stack.push(20);
 stack.push(25);
 stack.display();
 }
}

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
//Q:3)
import java.text.NumberFormat;
import java.util.Locale;
public class Employee {
 private int id;
 private String name;
 private double salary;
 public Employee(int id, String name, double salary) {
 this.id = id;
 this.name = name;
 this.salary = salary;
 }
 public void raiseSalary(double percent) {
 if (percent > 0) {
 double raiseAmount = (percent / 100) * salary;
 salary += raiseAmount;
 }
 }
 public void displayEmployeeDetails() {
 System.out.println("Employee ID: " + id);
 System.out.println("Employee Name: " + name);
 NumberFormat indianCurrencyFormat = NumberFormat.getCurrencyInstance(new
Locale("en", "IN"));
 System.out.println("Employee Salary: " + indianCurrencyFormat.format(salary));
 }
 public static void main(String[] args) {
 // Create an Employee object
 Employee emp1 = new Employee(101, "John Doe", 50000.0);
 // Display initial employee details
 System.out.println("Initial Employee Details:");
 emp1.displayEmployeeDetails();
 // Give the employee a 10% raise
 emp1.raiseSalary(10);
 // Display updated employee details
 System.out.println("\nEmployee Details After Raise:");
 emp1.displayEmployeeDetails();
 }
}

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
//Q:4)
class MyPoint {
 private int x;
 private int y;
 // Default constructor
 public MyPoint() {
 this.x = 0;
 this.y = 0;
 }
 // Overloaded constructor
 public MyPoint(int x, int y) {
 this.x = x;
 this.y = y;
 }
 public void setXY(int x, int y) {
 this.x = x;
 this.y = y;
 }
 public int[] getXY() {
 int[] coordinates = {x, y};
 return coordinates;
 }
 @Override
 public String toString() {
 return "(" + x + ", " + y + ")";
 }
 public double distance(int x, int y) {
 int dx = this.x - x;
 int dy = this.y - y;
 return Math.sqrt(dx * dx + dy * dy);
 }
 public double distance(MyPoint another) {
 return distance(another.x, another.y);
 }
 public double distance() {
 return distance(0, 0);
 }
}
public class TestMyPoint {
 public static void main(String[] args) {
 MyPoint point1 = new MyPoint(); // Default constructor (0, 0)
 MyPoint point2 = new MyPoint(3, 4); // Overloaded constructor (3, 4)
 // Testing setXY and getXY methods
 point1.setXY(1, 2);
 // Display point1's coordinates
 System.out.println("Point 1 coordinates: " + point1.toString());
 // Testing distance methods
 double distance1 = point1.distance(point2); // Distance between point1 and point2
 double distance2 = point1.distance(); // Distance between point1 and the origin (0,0)
 System.out.println("Distance between Point 1 and Point 2: " + distance1);
 System.out.println("Distance between Point 1 and the origin: " + distance2);
 }
}
 
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
//Q:5)
class Shape {
 public void draw() {
 System.out.println("Drawing a shape");
 }
 public void erase() {
 System.out.println("Erasing a shape");
 }
}
class Circle extends Shape {
 @Override
 public void draw() {
 System.out.println("Drawing a circle");
 }
 @Override
 public void erase() {
 System.out.println("Erasing a circle");
 }
}
class Triangle extends Shape {
 @Override
 public void draw() {
 System.out.println("Drawing a triangle");
 }
 @Override
 public void erase() {
 System.out.println("Erasing a triangle");
 }
}
class Square extends Shape {
 @Override
 public void draw() {
 System.out.println("Drawing a square");
 }
 @Override
 public void erase() {
 System.out.println("Erasing a square");
 }
}
public class Main {
 public static void main(String[] args) {
 Shape[] shapes = new Shape[3];
 shapes[0] = new Circle();
 shapes[1] = new Triangle();
 shapes[2] = new Square();
 for (Shape shape : shapes) {
 shape.draw();
 shape.erase();
 System.out.println();
 }
 }
}

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
//Q:6)
abstract class Shape {
 // Abstract method to calculate the area
 public abstract double calculateArea();
 // Abstract method to calculate the perimeter
 public abstract double calculatePerimeter();
}
class Circle extends Shape {
 private double radius;
 // Constructor
 public Circle(double radius) {
 this.radius = radius;
 }
 @Override
 public double calculateArea() {
 return Math.PI * radius * radius;
 }
 @Override
 public double calculatePerimeter() {
 return 2 * Math.PI * radius;
 }
}
class Triangle extends Shape {
 private double side1;
 private double side2;
 private double side3;
 // Constructor
 public Triangle(double side1, double side2, double side3) {
 this.side1 = side1;
 this.side2 = side2;
 this.side3 = side3;
 }
 @Override
 public double calculateArea() {
 // Using Heron's formula to calculate the area of a triangle
 double s = (side1 + side2 + side3) / 2.0;
 return Math.sqrt(s * (s - side1) * (s - side2) * (s - side3));
 }
 @Override
 public double calculatePerimeter() {
 return side1 + side2 + side3;
 }
}
public class Main {
 public static void main(String[] args) {
 Circle circle = new Circle(5.0);
 System.out.println("Circle - Area: " + circle.calculateArea());
 System.out.println("Circle - Perimeter: " + circle.calculatePerimeter());
 Triangle triangle = new Triangle(3.0, 4.0, 5.0);
 System.out.println("Triangle - Area: " + triangle.calculateArea());
 System.out.println("Triangle - Perimeter: " + triangle.calculatePerimeter());
 }
}


------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
//Q:7)
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
//Q:8)
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
//Q:9)
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
//Q:10)
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
//Q:11)
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
//Q:12)
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
