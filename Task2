/* TASK TWO: STUDENT GRADE TRACKER
Develop a Java program to track and manage student grades. 
The program should allow the user to input grades for different subjects or assignments, 
calculate the average grade, and display the overall grade along with any additional information 
(such as letter grade or GPA). */

import java.util.Scanner;

public class StudentGradeTracker {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String[] subjects = {"English", "Hindi", "Marathi", "Maths", "Science", "History", "Geography"};
        double[] grades = new double[subjects.length];

        System.out.println("----Student Grade Tracker----");
        System.out.println("Enter grades for the following subjects.");
        System.out.println("Type 'Exit' to exit the program.");
        System.out.println("Type 'Calculate' to calculate the average for entered grades.");
        System.out.println("--------------------------------");

        int enteredCount = 0; // Tracks the number of entered grades

        // Input grades
        for (int i = 0; i < subjects.length; i++) {
            while (true) {
                System.out.print("Enter (" + subjects[i] + ") Grade (0-100): ");
                String input = sc.next();

                if (input.equalsIgnoreCase("Exit")) {
                    System.out.println("Exiting program. Goodbye!");
                    return; // Exit the program
                }

                if (input.equalsIgnoreCase("Calculate")) {
                    // Calculate the entered grades and exit
                    if (enteredCount == 0) {
                        System.out.println("No grades entered. Exiting program.");
                        return;
                    }
                    calculateAndDisplayGrades(subjects, grades, enteredCount);
                    return; // Exit the program after calculation
                }

                try {
                    double grade = Double.parseDouble(input);
                    if (grade >= 0 && grade <= 100) {
                        grades[i] = grade;
                        enteredCount++;
                        break; // Proceed to the next subject
                    } else {
                        System.out.println("Invalid grade. Please enter a value between 0 and 100.");
                    }
                } catch (NumberFormatException e) {
                    System.out.println("Invalid input. Please enter a numeric grade, 'Calculate', or 'Exit'.");
                }
            }
        }

        System.out.println("--------------------------------");

        // Final calculation if all grades are entered
        if (enteredCount > 0) {
            calculateAndDisplayGrades(subjects, grades, enteredCount);
        }
    }

    private static void calculateAndDisplayGrades(String[] subjects, double[] grades, int count) {
        // Calculate average grade
        double total = 0;
        for (int i = 0; i < count; i++) {
            total += grades[i];
        }

        double average = total / count;

        // Determine letter grade
        String letterGrade;
        if (average >= 90) {
            letterGrade = "A";
        } else if (average >= 80) {
            letterGrade = "B";
        } else if (average >= 70) {
            letterGrade = "C";
        } else if (average >= 60) {
            letterGrade = "D";
        } else {
            letterGrade = "F";
        }

        // Calculate GPA (on a 4.0 scale)
        double gpa;
        if (average >= 90) {
            gpa = 4.0;
        } else if (average >= 80) {
            gpa = 3.0;
        } else if (average >= 70) {
            gpa = 2.0;
        } else if (average >= 60) {
            gpa = 1.0;
        } else {
            gpa = 0.0;
        }

        // Display results
        System.out.println("\n-----Student Grade Summary-----");
        for (int i = 0; i < count; i++) {
            System.out.printf("%s Grade: %.2f\n", subjects[i], grades[i]);
        }
        System.out.println("--------------------------------");
        System.out.printf("Average Grade: %.2f\n", average);
        System.out.println("Letter Grade: " + letterGrade);
        System.out.printf("GPA: %.2f\n", gpa);
    }
}
