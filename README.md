import java.util.*;

class Student {
    String rollNo;
    String name;
    Map<String, Integer> marks;
    
    Student(String rollNo, String name, Map<String,Integer> marks) {
        this.rollNo = rollNo;
        this.name = name;
        this.marks = marks;
    }
    subjects: ");
        int n = sc.nextInt();
        sc.nextLine();
        for (int i = 0; i < n; i++) {
            System.out.print("Enter subject name: ");
            String sub = sc.nextLine();
            System.out.print("Enter marks in " + sub + ": ");
            int mark = sc.nextInt();
            sc.nextLine();
            marks.put(sub, mark);
        }
        students.put(roll, new Student(roll, name, marks));
        System.out.println("Student added successfully!");
    }
    
    static void viewStudentResult() {
        System.out.print("Enter Roll No: ");
        String roll = sc.nextLine();
        Student s = students.get(roll);
        if (s == null) {
            System.out.println("No such student!");
            return;
        }
        printResult(s);
    }
    
    static void viewAllResults() {
        if (students.isEmpty()) {
            System.out.println("No student records!");
            return;
        }
        for (Student s : students.values()) {
            printResult(s);
            System.out.println("-------------");
        }
    }
    
    static void printResult(Student s) {
        System.out.println("Roll No: " + s.rollNo);
        System.out.println("Name: " + s.name);
        System.out.println("Marks:");
        for (Map.Entry<String, Integer> entry : s.marks.entrySet()) {
            System.out.println("  " + entry.getKey() + ": " + entry.getValue());
        }
        System.out.println("Total: " + s.getTotal());
        System.out.printf("Percentage: %.2f\n", s.getPercentage());
        System.out.println("Grade: " + s.getGrade());
        System.out.println("Result: " + (s.isPass() ? "Pass" : "Fail"));
    }
}
