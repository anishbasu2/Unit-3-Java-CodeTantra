# Unit-3-Java-CodeTantra

36.1.1

As per statement 5, Z2 is the subclass of Y, X and Object

36.1.2

import java.util.Scanner;
class Person {
    String name;
    int age;
    public void getInfo() {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter the name: ");
        name = scanner.nextLine();
        System.out.print("Enter the age: ");
        age = scanner.nextInt();
    }
    public void displayInfo() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
    }
}
class Student extends Person {
    int rollNumber;
    @Override
    public void getInfo() {
        super.getInfo();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter the roll number: ");
        rollNumber = scanner.nextInt();
    }
    @Override
    public void displayInfo() {
        super.displayInfo();
        System.out.println("Roll Number: " + rollNumber);
    }
}
public class InheritanceExample{
    public static void main(String[] args) {
        Student student = new Student();
        student.getInfo();
        student.displayInfo();
    }
}

36.1.3

import java.util.Scanner;
class A {    
    public int aValue;
    public int getAValue() {
      return aValue;
    }
}
class B extends A {
    public int bValue;
    public int getBValue() {
        return bValue;
    }
}
public class InheritanceExample2 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        B b = new B();
        System.out.print("Enter the value for A: ");
        b.aValue = scanner.nextInt();       
        System.out.print("Enter the value for B: ");
        b.bValue = scanner.nextInt();
        System.out.println("b.getAValue(): " + b.getAValue());
        System.out.println("b.getBValue(): " + b.getBValue());
    }
}












36.1.4

class Marks {
    int id;
    float javaMarks, cMarks, cppMarks;
    public void setMarks(int id, float javaMarks, float cMarks, float cppMarks) {
        this.id = id;
        this.javaMarks = javaMarks;
        this.cMarks = cMarks;
        this.cppMarks = cppMarks;
    }
    public void displayMarks() {
        System.out.println("Id : " + id);
        System.out.println("Java marks : " + javaMarks);
        System.out.println("C marks : " + cMarks);
        System.out.println("Cpp marks : " + cppMarks);
    }
}
class Result extends Marks {
    float total, avg;
    public void compute() {
        total = javaMarks + cMarks + cppMarks;
        avg = total / 3;
    }
    public void showResult() {
        System.out.println("Total : " + total);
        System.out.println("Avg : " + avg);
    }
}

public class SingleInheritanceDemo {
    public static void main(String[] args) {
        if (args.length != 4) {
            System.out.println("Please provide four arguments: id, javaMarks, cMarks, cppMarks");
            return;
        }
        int id = Integer.parseInt(args[0]);
        float javaMarks = Float.parseFloat(args[1]);
        float cMarks = Float.parseFloat(args[2]);
        float cppMarks = Float.parseFloat(args[3]);
        Result result = new Result();
        result.setMarks(id, javaMarks, cMarks, cppMarks);
        result.displayMarks();
        result.compute();
        result.showResult();
    }
}



36.1.5


class Student {
    int id;
    String name;
    public void setData(int id, String name) {
        this.id = id;
        this.name = name;
    }
    public void displayData() {
        System.out.println("Id : " + id);
        System.out.println("Name : " + name);
    }
}
class Marks extends Student {
    float javaMarks, cMarks, cppMarks;
    public void setMarks(float javaMarks, float cMarks, float cppMarks) {
        this.javaMarks = javaMarks;
        this.cMarks = cMarks;
        this.cppMarks = cppMarks;
    }
    public void displayMarks() {
        System.out.println("Java marks : " + javaMarks);
        System.out.println("C marks : " + cMarks);
        System.out.println("Cpp marks : " + cppMarks);
    }
}
class Result extends Marks {
    float total, avg;
    public void compute() {
        total = javaMarks + cMarks + cppMarks;
        avg = total / 3;
    }
    public void showResult() {
        System.out.println("Total : " + total);
        System.out.println("Avg : " + avg);
    }
}

public class MultilevelInheritanceDemo {
    public static void main(String[] args) {
        if (args.length != 5) {
            System.out.println("Please provide five arguments: id, name, javaMarks, cMarks, cppMarks");
            return;
        }
        int id = Integer.parseInt(args[0]);
        String name = args[1];
        float javaMarks = Float.parseFloat(args[2]);
        float cMarks = Float.parseFloat(args[3]);
        float cppMarks = Float.parseFloat(args[4]);
        Result result = new Result();
        result.setData(id, name);
        result.setMarks(javaMarks, cMarks, cppMarks);
        result.displayData();
        result.displayMarks();
        result.compute();
        result.showResult();
    }
}

Test After 36

Addition and Multiplication using Inheritance


import java.util.Scanner;

class Calculation {
    public int num1, num2;
    public Calculation(int num1, int num2) {
        this.num1 = num1;
        this.num2 = num2;
    }
    public int addition() {
        return num1 + num2;
    }
}

class My_Calculation extends Calculation {
    public My_Calculation(int num1, int num2) {
        super(num1, num2);
    }
    public int multiplication() {
        return num1 * num2;
    }
}

public class MainCalculation {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int num1 = scanner.nextInt();
        int num2 = scanner.nextInt();
        My_Calculation myCalculation = new My_Calculation(num1, num2);
        int additionResult = myCalculation.addition();
        int multiplicationResult = myCalculation.multiplication();
        System.out.println(additionResult);
        System.out.println(multiplicationResult);
    }
}



Test after 36


Banking System -single Inheritance



import java.util.Scanner;

class Account {
    String accountNumber;
    double balance;
    public void inputDetails() {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter account number: ");
        accountNumber = scanner.nextLine();
    }
    public void displayBalance() {
        System.out.println("Current balance: " + balance);
    }
}

class Transaction extends Account {
    double amount;
    public void inputAmount() {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter transaction amount: ");
        amount = scanner.nextDouble();
    }
    public void performTransaction() {
        balance += amount;
        System.out.println("Transaction Successful!");
        displayBalance();
    }
}

public class BankingSystem {
    public static void main(String[] args) {
        Transaction transaction = new Transaction();
        transaction.inputDetails();
        transaction.displayBalance();
        transaction.inputAmount();
        transaction.performTransaction();
    }








Test after 36

Person's name and age- Single inheritance



import java.util.Scanner;

class Person {
    String name;
    public void inputName() {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter name: ");
        name = scanner.nextLine();
    }
    public void displayName() {
        System.out.println("Name: " + name);
    }
}
class Citizen extends Person {
    int age;
    public void inputAge() {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter age: ");
        age = scanner.nextInt();
    }
    public void displayAge() {
        System.out.println("Age: " + age);
    }
}

public class MainPerson {
    public static void main(String[] args) {
        Citizen citizen = new Citizen();
        citizen.inputName();
        citizen.displayName();
        citizen.inputAge();
        citizen.displayAge();
    }
}






Test after 36


Temperature conversion -single Inheritance

import java.util.Scanner;

class Temperature {
    float celsius;
    float fahrenheit;
    public void inputTemperature() {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter temperature in Celsius: ");
        celsius = scanner.nextFloat();
    }
}

class Conversion extends Temperature {
    public void convertToFahrenheit() {
        fahrenheit = (celsius * 9 / 5) + 32;
        System.out.printf("Temperature in Fahrenheit: %.2f%n", fahrenheit);
    }
}

public class MainTemp {
    public static void main(String[] args) {
        Conversion conversion = new Conversion();
        conversion.inputTemperature();
        conversion.convertToFahrenheit();
    }
}





37.1.1


charAt method is not overloaded.


indexOf method is overloaded 4 times.


The String constructor is overloaded 15 times








37.1.2



public class Addition {
	static void add(int x,int y){
		System.out.println("Sum of "+x+" and "+y+" : "+(x+y));
	}
	static void add(int x,float y){
		System.out.println("Sum of "+x+" and "+y+" : "+(x+y));
	}
	static void add(float x,float y){
		System.out.println("Sum of "+x+" and "+y+" : "+(x+y));
	}
	static void add(float x,double y, double z){
		System.out.println("Sum of "+x+", "+y+" and "+z+" : "+(x+y+z));
	}
	public static void main(String[] args){
		int a = Integer.parseInt(args[0]);
		int b = Integer.parseInt(args[1]);
		Float c = Float.parseFloat(args[2]);
		Float d = Float.parseFloat(args[3]);
		double e = Double.parseDouble(args[4]);
		double f = Double.parseDouble(args[5]);
		add(a,b);
		add(c,d);
		add(b,d);
		add(c,e,f);
	}
}







37.1.3




public class Box{
	double width , height , depth;
	Box(){
		width = -1;
		height = -1;
		depth = -1;
	}
	Box(double L){
		width = L;
		height = L;
		depth = L;
	}
	Box(double w ,double h , double d){
		width = w;
		height = h;
		depth = d;
	}
	public double volume(){
		return width*height*depth;
	}
	public static void main(String...args){
		double a,b,c;
		if(args.length==0){
			Box obj = new Box();
			System.out.println("Volume of Box() is : "+obj.volume());
		}
		if(args.length==1){
			a = Double.parseDouble(args[0]);
			Box obj = new Box(a);
			System.out.println("Volume of Box("+a+") is : "+obj.volume());
		} 
		else if(args.length==3){
			a = Double.parseDouble(args[0]);
			b = Double.parseDouble(args[1]);
			c = Double.parseDouble(args[2]);
			Box obj = new Box(a,b,c);
			System.out.println("Volume of Box("+a+", "+b+", "+c+")"+" is : "+obj.volume());
		}
	}
}










37.1.4


public class OverloadArea {
	// Write the overload methods
	static float area(float a){
		return a*a;
	}
	static float area(float a,float b){
		return a*b;
	}
	public static void main (String[] args) {
		// Write the code
		Float f1 = Float.parseFloat(args[0]);
		Float f2 = Float.parseFloat(args[1]);
		System.out.println("Area of square for side in meters " + f1 + " : " +area(f1) ); // Fill in the missing code
		System.out.println("Area of rectangle for length and breadth in meters " + f1 + ", " + f2 + " : " +area(f1,f2) ); // Fill in the missing code
	}
}





Test after 37

Rectangle area

import java.util.Scanner;

class RectangleIn {
    int length;
    int width;
    public void inputDimensions() {
        Scanner scanner = new Scanner(System.in);
        System.out.print("length: ");
        length = scanner.nextInt();
        System.out.print("width: ");
        width = scanner.nextInt();
    }
}

class AreaOut extends RectangleIn {
    public void calculateArea() {
        int area = length * width;
        System.out.println("Area: " + area);
    }
}

public class Main {
    public static void main(String[] args) {
        AreaOut obj = new AreaOut();
        obj.inputDimensions();
        obj.calculateArea();
    }
}







Test after 37

Car Info
import java.util.Scanner;

class Vehicle {
    String make;
    String model;
}

class CarInfo extends Vehicle {
    public void inputCarDetails() {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter car make: ");
        make = scanner.nextLine();
        System.out.print("Enter car model: ");
        model = scanner.nextLine();
    }
    public void displayCarInfo() {
        System.out.println("Car Make: " + make);
        System.out.println("Car Model: " + model);
    }
}

public class Main {
    public static void main(String[] args) {
        CarInfo car = new CarInfo();
        car.inputCarDetails();
        car.displayCarInfo();
    }
}








Test after 37


Employee Salary


import java.util.Scanner;

class Employee {
    String employeeName;
    String designation;
    int yearsOfExperience;
}

class EmployeeInfo extends Employee {
    double salaryPerYear;
    public void inputEmployeeDetails() {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter employee name: ");
        employeeName = scanner.nextLine();
        System.out.print("Enter employee designation: ");
        designation = scanner.nextLine();
        System.out.print("Enter years of experience: ");
        yearsOfExperience = scanner.nextInt();
        System.out.print("Enter salary per year: $");
        salaryPerYear = scanner.nextDouble();
    }
    public void displayEmployeeInfo() {
        System.out.println("Employee Name: " + employeeName);
        System.out.println("Designation: " + designation);
        System.out.println("Years of Experience: " + yearsOfExperience + " years");
    }
    public void calculateSalary() {
        double salary = yearsOfExperience * salaryPerYear;
        System.out.println("Salary: $" + salary);
    }
}

public class Main {
    public static void main(String[] args) {
        EmployeeInfo employee = new EmployeeInfo();
        employee.inputEmployeeDetails();
        employee.displayEmployeeInfo();
        employee.calculateSalary();
    }
}



Test after 37




Circle Area



import java.util.Scanner;

class CircleIn {
    double radius;
    public void inputRadius() {
        Scanner scanner = new Scanner(System.in);
        System.out.print("radius: ");
        radius = scanner.nextDouble();
    }
}
class CircumferenceAndAreaOut extends CircleIn {
    public void calculateCircumference() {
        double circumference = 2 * Math.PI * radius;
        System.out.println("Circumference: " + circumference);
    }
    public void calculateArea() {
        double area = Math.PI * radius * radius;
        System.out.println("Area: " + area);
    }
}

public class Main {
    public static void main(String[] args) {
        CircumferenceAndAreaOut circle = new CircumferenceAndAreaOut();
        circle.inputRadius();
        circle.calculateCircumference();
        circle.calculateArea();
    }
}



38.1.1


import java.util.Scanner;

class A {
    public int aValue;
    public int getAValue() {
        return aValue;
    }
}

class B extends A {
    public int bValue;
    public int getBValue() {
        return bValue;
    }
    public int getAValue() {
        return 2 * super.getAValue(); // overriding method to access superclass method implementation
    }
}

public class OverridingExample{
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        B b = new B();
        System.out.print("Enter the value for A: ");
        b.aValue = scanner.nextInt();
        System.out.print("Enter the value for B: ");
        b.bValue = scanner.nextInt();
        System.out.println("b.getAValue(): " + b.getAValue());
        System.out.println("b.getBValue(): " + b.getBValue());
    }
}







38.1.2



Statements 1, 2 and 3 in class A contain overloaded versions of method printMe


The method in statement 4, overrides the method declared in statement 1









38.1.3



class Bank {
    public float calculateInterest(float principal, int time) {
        return 0;
    }
}

class SBI extends Bank {
    public static final float INTEREST_RATE = 10.8f;
    @Override
    public float calculateInterest(float principal, int time) {
        return (principal * INTEREST_RATE * time) / 100;
    }
}

class ICICI extends Bank {
    public static final float INTEREST_RATE = 11.6f;
    @Override
    public float calculateInterest(float principal, int time) {
        return (principal * INTEREST_RATE * time) / 100;
    }
}

class AXIS extends Bank {
    public static final float INTEREST_RATE = 12.3f;
    @Override
    public float calculateInterest(float principal, int time) {
        return (principal * INTEREST_RATE * time) / 100;
    }
}

public class TestOverriding{
    public static void main(String[] args) {
        float principal = Float.parseFloat(args[0]);
        int time = Integer.parseInt(args[1]);
        SBI sbi = new SBI();
        ICICI icici = new ICICI();
        AXIS axis = new AXIS();
        System.out.println("SBI rate of interest = " + sbi.calculateInterest(principal, time));
        System.out.println("ICICI rate of interest = " + icici.calculateInterest(principal, time));
        System.out.println("AXIS rate of interest = " + axis.calculateInterest(principal, time));
    }
}





39.1.1


package q11272;

class SuperClass {
    int num;
    public SuperClass(int value) {
        num = value;
        System.out.println("SuperClass number = " + 10);
    }
    public void printHello() {
        System.out.println("Hello from SuperClass");
    }
}
class SubClass extends SuperClass {
    public SubClass(int value) {
        super(value + 5);
        System.out.println("SubClass number = " + num);
    }
    @Override
    public void printHello() {
        super.printHello();
        System.out.println("Hello from SubClass");
    }
}
public class SuperKeyword {
    public static void main(String[] args) {
        SubClass obj = new SubClass(10);
        obj.printHello();
    }
}







39.1.2


class Animal {
    public Animal() {
        System.out.println("Animal is created");
    }
    public void eat() {
        System.out.println("Eating something");
    }
}

class Dog extends Animal {
    public Dog() {
        super();
        System.out.println("Dog is created");
    }
    @Override
    public void eat() {
        System.out.println("Eating bread");
    }
    public void bark() {
        System.out.println("Barking");
    }
    public void work() {
        super.eat();
        eat();
        bark();
    }
}
public class ExampleOnSuper {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.work();
    }
}






39.1.3





class SuperClass {
    int value1;
    int value2;
    public SuperClass(int value1, int value2) {
        this.value1 = value1;
        this.value2 = value2;
    }
    public void show() {
        System.out.println("This is super class show() method");
        System.out.println("value1 = " + value1);
        System.out.println("value2 from super class = " + value2);
    }
}
class SubClass extends SuperClass {
    int value3;
    int value4;
    public SubClass(int value1, int value2, int value3, int value4) {
        super(value1, value2);
        this.value3 = value3;
        this.value4 = value4;
    }
    public void show() {
        System.out.println("This is sub class show() method");
        super.show();
        System.out.println("value3 = " + value3);
        System.out.println("value4 = " + value4);
    }
}
public class AccessUsingSuper {
    public static void main(String[] args) {
        int value1 = Integer.parseInt(args[0]);
        int value2 = Integer.parseInt(args[1]);
        int value3 = Integer.parseInt(args[2]);
        int value4 = Integer.parseInt(args[3]);
        SubClass obj = new SubClass(value1, value2, value3, value4);
        obj.show();
    }
}





40.1.1


Object a = new A();
        Object b = new B();
        Object c = new C();



40.1.2



class Animal {
    public void whoAmI() {
        System.out.println("I am a generic animal");
    }
}

class Dog extends Animal {
    @Override
    public void whoAmI() {
        System.out.println("I am a dog");
    }
}

class Cow extends Animal {
    @Override
    public void whoAmI() {
        System.out.println("I am a cow");
    }
}

class Snake extends Animal {
    @Override
    public void whoAmI() {
        System.out.println("I am a snake");
    }
}





41.1.1


No. It is not allowed







42.1.1



class A {
    private int value;
    public A(int value) {
        this.value = value;
    }
    @Override
    public String toString() {
        return "The value is: " + value;
    }
}






42.1.2





class A {
    private int value;
    public A(int value) {
        this.value = value;
    }
    @Override
    public boolean equals(Object otherObject) {
        if (this == otherObject) {
            return true;
        }
        if (otherObject instanceof A) {
            A otherARef = (A) otherObject;
            return this.value == otherARef.value;
        }
        return false;
    }
}
class B {
    private int value;
    public B(int value) {
        this.value = value;
    }
    // No need to override equals() method for class B in this example
}

class EqualsExample{
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("a1: ");
        A a1 = new A(scanner.nextInt());
        System.out.print("a2: ");
        A a2 = new A(scanner.nextInt());
        System.out.print("a3: ");
        A a3 = new A(scanner.nextInt());
        System.out.println("a1.equals(a2) : " + a1.equals(a2));
        System.out.println("a1.equals(a3) : " + a1.equals(a3));
        System.out.print("b1: ");
        B b1 = new B(scanner.nextInt());
        System.out.print("b2: ");
        B b2 = new B(scanner.nextInt());
        System.out.print("b3: ");
        B b3 = new B(scanner.nextInt());
        System.out.println("b1.equals(b2) : " + b1.equals(b2));
        System.out.println("b1.equals(b3) : " + b1.equals(b3));
        scanner.close();
    }
}





42.2.1


Statements 3 and 4 will produce compiler errors saying value2 cannot be resolved, since value2 is neither declared locally in the enclosing block nor as a field in the class






Test after 42

CustomObject Class with Customized toString() Method Implementation


package q22058;
import java.util.Scanner
class CustomObject {
    private String attribute1;
    private int attribute2;
    public CustomObject(String attribute1, int attribute2) {
        this.attribute1 = attribute1;
        this.attribute2 = attribute2;
    }
    @Override
    public String toString() {
        return "CustomObject{attribute1='" + attribute1 + "', attribute2=" + attribute2 + "}";
    }
}





Test after 42

a class Car for managing autonomous car


import java.util.Scanner;

public class Car {
    private String make;
    private String model;
    private boolean autonomousMode;
    public Car(String make, String model) {
        this.make = make;
        this.model = model;
        this.autonomousMode = false;
    }
    public void startAutonomous() {
        autonomousMode = true;
        System.out.println("Autonomous mode activated. Enjoy your ride in the " + make + " " + model + "!");
    }
    public void stopAutonomous() {
        autonomousMode = false;
        System.out.println("Autonomous mode deactivated. Your " + make + " " + model + " is now under manual control.");
    }
}





43.1.1



Statement 2 will result in a compilation error because we cannot instantiate an interface


Statements 4 and 5 do not result in compilation errors









Test after 43



Area and Perimeter of Circle

import java.util.Scanner;

interface Shape {
    double calculateArea();
    double calculatePerimeter();
}

class Circle implements Shape {
    private double radius;
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
public class AreaCalc {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Radius: ");
        double radius = scanner.nextDouble();
        Circle circle = new Circle(radius);
        System.out.printf("Area: %.2f%n", circle.calculateArea());
        System.out.printf("Perimeter: %.2f%n", circle.calculatePerimeter());
        scanner.close();
    }
}




Test after 43


Music Player Application

import java.util.Scanner;

interface Playable {
    void play();
}

class MP3Player implements Playable {
    @Override
    public void play() {
        System.out.println("Playing MP3 audio");
    }
}

class WAVPlayer implements Playable {
    @Override
    public void play() {
        System.out.println("Playing WAV audio");
    }
}

class MusicPlayer {
    public void playAudio(Playable audio) {
        audio.play();
    }
}

public class PlayerMain {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        MP3Player mp3Player = new MP3Player();
        WAVPlayer wavPlayer = new WAVPlayer();
        MusicPlayer musicPlayer = new MusicPlayer();
        System.out.println("Choose an audio format:");
        System.out.println("1. MP3");
        System.out.println("2. WAV");
        int choice = scanner.nextInt();
        switch (choice) {
            case 1:
                musicPlayer.playAudio(mp3Player);
                break;
            case 2:
                musicPlayer.playAudio(wavPlayer);
                break;
            default:
                System.out.println("Invalid choice");
        }
        scanner.close();
    }
}





Test after 43


Numerical sorting application

import java.util.Scanner;
import java.util.Arrays;
interface NumberSorter {
    void sort(int[] numbers);
}

class AscendingSorter implements NumberSorter {
    @Override
    public void sort(int[] numbers) {
        Arrays.sort(numbers);
        System.out.println("Ascending Order:");
        for (int num : numbers) {
            System.out.print(num + " ");
        }
        System.out.println();
    }
}

class DescendingSorter implements NumberSorter {
    @Override
    public void sort(int[] numbers) {
        Arrays.sort(numbers);
        System.out.println("Descending Order:");
        for (int i = numbers.length - 1; i >= 0; i--) {
            System.out.print(numbers[i] + " ");
        }
        System.out.println();
    }
}

public class SortArray {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Size of the array: ");
        int size = scanner.nextInt();
        int[] numbers = new int[size];
        System.out.println("Elements of the array:");
        for (int i = 0; i < size; i++) {
            System.out.print("Element " + (i + 1) + ": ");
            numbers[i] = scanner.nextInt();
        }
        NumberSorter ascendingSorter = new AscendingSorter();
        ascendingSorter.sort(numbers);
        NumberSorter descendingSorter = new DescendingSorter();
        descendingSorter.sort(numbers);
        scanner.close();
    }
}





44.1.1



import java.util.Scanner;

interface Printable {
    void print();
}

class Document implements Printable {
    public void print() {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter the first value: ");
        int firstValue = scanner.nextInt();
        System.out.print("Enter the second value: ");
        int secondValue = scanner.nextInt();
        System.out.println("You entered: " + firstValue + " and " + secondValue);
        scanner.close();
    }
}

public class Main {
    public static void main(String[] args) {
        Printable document = new Document();
        document.print();
    }
}












44.1.2



interface Car {
    String getName();
    int getMaxSpeed();
    default void applyBreak() {
        System.out.println("Applying break on " + getName());
    }
    static Car getFastestCar(Car car1, Car car2) {
        return car1.getMaxSpeed() >= car2.getMaxSpeed() ? car1 : car2;
    }
}

class BMW implements Car {
    private String name;
    private int maxSpeed;
    public BMW(String name, int maxSpeed) {
        this.name = name;
        this.maxSpeed = maxSpeed;
    }
    public String getName() {
        return name;
    }
    public int getMaxSpeed() {
        return maxSpeed;
    }
}

class Audi implements Car {
    private String name;
    private int maxSpeed;
    public Audi(String name, int maxSpeed) {
        this.name = name;
        this.maxSpeed = maxSpeed;
    }
    public String getName() {
        return name;
    }
    public int getMaxSpeed() {
        return maxSpeed;
    }
}

public class MainApp {
    public static void main(String[] args) {
        // Assuming correct command line arguments format: "Name MaxSpeed Name MaxSpeed"
        if (args.length != 4) {
            System.out.println("Invalid number of arguments.");
            return;
        }
        String bmwName = args[0];
        int bmwMaxSpeed = Integer.parseInt(args[1]);
        String audiName = args[2];
        int audiMaxSpeed = Integer.parseInt(args[3]);
        Car bmw = new BMW(bmwName, bmwMaxSpeed);
        Car audi = new Audi(audiName, audiMaxSpeed);
        Car fastestCar = Car.getFastestCar(bmw, audi);
        System.out.println("Fastest car is : " + fastestCar.getName());
    }
}










Test after 44

Binary Calculator


import java.util.Scanner;

interface BinaryOperation {
    void operate(String binaryNumber1, String binaryNumber2);
}

class BinaryAddition implements BinaryOperation {
    @Override
    public void operate(String binaryNumber1, String binaryNumber2) {
        int decimalNumber1 = Integer.parseInt(binaryNumber1, 2);
        int decimalNumber2 = Integer.parseInt(binaryNumber2, 2);
        int sum = decimalNumber1 + decimalNumber2;
        String binarySum = Integer.toBinaryString(sum);
        System.out.println("Binary Addition Result: " + binarySum);
    }
}

class BinaryMultiplication implements BinaryOperation {
    @Override
    public void operate(String binaryNumber1, String binaryNumber2) {
        int decimalNumber1 = Integer.parseInt(binaryNumber1, 2);
        int decimalNumber2 = Integer.parseInt(binaryNumber2, 2);
        int product = decimalNumber1 * decimalNumber2;
        String binaryProduct = Integer.toBinaryString(product);
        System.out.println("Binary Multiplication Result: " + binaryProduct);
    }
}

public class BinaryCalc {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter the binary numbers for addition and multiplication: ");
        String binaryNumbers = scanner.nextLine();
        String[] binaryArray = binaryNumbers.split(" ");
        BinaryOperation binaryAddition = new BinaryAddition();
        binaryAddition.operate(binaryArray[0], binaryArray[1]);
        BinaryOperation binaryMultiplication = new BinaryMultiplication();
        binaryMultiplication.operate(binaryArray[0], binaryArray[1]);
        scanner.close();
    }
}











Test after 44

Password Checker


import java.util.Scanner;

interface PasswordChecker {
    int checkLength(String password);
    String checkComplexity(String password);
}

class SimplePasswordChecker implements PasswordChecker {
    @Override
    public int checkLength(String password) {
        int length = password.length();
        System.out.print("Length: ");
        return length;
    }
    @Override
    public String checkComplexity(String password) {
        int length = password.length();
        if (length < 8) {
            return "Weak";
        } else if (length == 8) {
            return "Medium";
        } else {
            return "Strong";
        }
    }
}

public class CheckPassword {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a password: ");
        String password = scanner.nextLine();
        PasswordChecker simpleChecker = new SimplePasswordChecker();
        simpleChecker.checkLength(password);
        System.out.println(simpleChecker.checkComplexity(password));
        scanner.close();
    }
}









Test after 44


Calculator Interface


import java.util.Scanner;

interface Calculator {
    double add(double a, double b);
    double subtract(double a, double b);
    double multiply(double a, double b);
    double divide(double a, double b);
}

class BasicCalculator implements Calculator {
    @Override
    public double add(double a, double b) {
        return a + b;
    }
    @Override
    public double subtract(double a, double b) {
        return a - b;
    }
    @Override
    public double multiply(double a, double b) {
        return a * b;
    }
    @Override
    public double divide(double a, double b) {
        if (b != 0) {
            return a / b;
        } else {
            System.out.println("Error: Division by zero");
            return Double.NaN; 
        }
    }
}

public class Calc {
    public static void main(String[] args) {
        Calculator calculator = new BasicCalculator();
        Scanner scanner = new Scanner(System.in);
        double a = scanner.nextDouble();
        double b = scanner.nextDouble();
        double result1 = calculator.add(a, b);
        double result2 = calculator.subtract(a, b);
        double result3 = calculator.multiply(a, b);
        double result4 = calculator.divide(a, b);
        System.out.println("Addition: " + result1);
        System.out.println("Subtraction: " + result2);
        System.out.println("Multiplication: " + result3);
        System.out.println("Division: " + result4);
        scanner.close();
    }
}







45.1.1

import java.util.Scanner;

abstract class CalcArea {
    abstract double triangleArea(double b, double h);
    abstract double rectangleArea(double l, double b);
    abstract double squareArea(double s);
    abstract double circleArea(double r);
}

class FindArea extends CalcArea {
    @Override
    double triangleArea(double b, double h) {
        return 0.5 * b * h;
    }
    @Override
    double rectangleArea(double l, double b) {
        return l * b;
    }
    @Override
    double squareArea(double s) {
        return s * s;
    }
    @Override
    double circleArea(double r) {
        return 3.14* r * r;
    }
}

public class Area {
    public static void main(String[] args) {
        if (args.length < 2) {
            System.out.println("Please provide two arguments.");
            return;
        }
        double arg1, arg2;
        try {
            arg1 = Double.parseDouble(args[0]);
            arg2 = Double.parseDouble(args[1]);
        } catch (NumberFormatException e) {
            System.out.println("Invalid input. Please provide valid numeric arguments.");
            return;
        }
        FindArea areaFinder = new FindArea();
        double triangleArea = areaFinder.triangleArea(arg1, arg2);
        double rectangleArea = areaFinder.rectangleArea(arg1, arg2);
        double squareArea = areaFinder.squareArea(arg1);
        double circleArea = areaFinder.circleArea(arg2);
        System.out.println("Area of triangle : " + triangleArea);
        System.out.println("Area of rectangle : " + rectangleArea);
        System.out.println("Area of square : " + squareArea);
        System.out.println("Area of circle : " + circleArea);
    }
}















45.1.2



abstract class Shape {
    abstract void numberOfSides();
}

class Trapezoid extends Shape {
    @Override
    void numberOfSides() {
        System.out.println("Number of sides in a trapezoid are 4");
    }
}

class Triangle extends Shape {
    @Override
    void numberOfSides() {
        System.out.println("Number of sides in a triangle are 3");
    }
}

class Hexagon extends Shape {
    @Override
    void numberOfSides() {
        System.out.println("Number of sides in a hexagon are 6");
    }
}

public class AbstractExample {
    public static void main(String[] args) {
        Shape shape;
        shape = new Trapezoid();
        shape.numberOfSides();
        shape = new Triangle();
        shape.numberOfSides();
        shape = new Hexagon();
        shape.numberOfSides();
    }
}






45.1.3


//Define the required abstract class here

abstract class AbstractGreeting implements Greeting {
    @Override
    public String getStandardMessage(String name) {
        return "Hi " + name;
    }
    public abstract String getCustomMessage(String name);
}







Test after 45



Coffee machine using abstraction


import java.util.Scanner;

abstract class CoffeeMachine {
    public abstract void brewCoffee(int cups);
    public abstract void addWater(int cups);
}

class BasicCoffeeMachine extends CoffeeMachine {
    @Override
    public void brewCoffee(int cups) {
        System.out.println("Brewing " + cups + " cups of basic coffee");
    }
    @Override
    public void addWater(int cups) {
        System.out.println("Adding " + cups + " cups of water to the coffee machine");
    }
}

public class Main {
    public static void main(String[] args) {
        BasicCoffeeMachine coffeeMachine = new BasicCoffeeMachine();
        Scanner scanner = new Scanner(System.in);
        System.out.print("cups of coffee: ");
        int coffeeCups = scanner.nextInt();
        System.out.print("cups of water: ");
        int waterCups = scanner.nextInt();
        coffeeMachine.addWater(waterCups);
        coffeeMachine.brewCoffee(coffeeCups);
        scanner.close();
    }
}






46.1.1

interface Animal {
    void makeSound();
    default String eatFood() {
        return "eating generic food";
    }
}

public class Dog implements Animal {
    @Override
    public void makeSound() {
        System.out.println("Dog barks: Woof! Woof!");
    }

    @Override
    public String eatFood() {
        return "Dog is eating bones";
    }
}
