import java.util.LinkedList;

public class Main {
    public static void main(String[] args) {
        LinkedList<Student> list1 = new LinkedList<>();
        list1.add(new Student("Иванов", 1, 4.5));
        list1.add(new Student("Петров", 5, 3.8));
        list1.add(new Student("Сидоров", 3, 4.9));

        LinkedList<Student> list2 = new LinkedList<>();
        list2.add(new Student("Кузнецов", 2, 4.1));
        list2.add(new Student("Смирнов", 4, 5.0));

        System.out.println("Список 1:");
        for (Student s : list1) System.out.println(s);
        System.out.println("Список 2:");
        for (Student s : list2) System.out.println(s);

        LinkedList<Student> merged = mergeSortedLists(list1, list2);
        
        System.out.println("\nОбъединённый отсортированный список:");
        for (Student s : merged) System.out.println(s);
    }

    static LinkedList<Student> mergeSortedLists(LinkedList<Student> a, LinkedList<Student> b) {
        LinkedList<Student> result = new LinkedList<>();
        LinkedList<Student> left = new LinkedList<>(a);
        LinkedList<Student> right = new LinkedList<>(b);

        left.sort((s1, s2) -> Integer.compare(s1.iDNumber, s2.iDNumber));
        right.sort((s1, s2) -> Integer.compare(s1.iDNumber, s2.iDNumber));

        while (!left.isEmpty() && !right.isEmpty()) {
            if (left.getFirst().iDNumber <= right.getFirst().iDNumber) {
                result.add(left.removeFirst());
            } else {
                result.add(right.removeFirst());
            }
        }
        while (!left.isEmpty()) {
            result.add(left.removeFirst());
        }
        while (!right.isEmpty()) {
            result.add(right.removeFirst());
        }
        return result;
    }
}

class Student {
    String name;
    int iDNumber;
    double gpa;

    Student(String name, int iDNumber, double gpa) {
        this.name = name;
        this.iDNumber = iDNumber;
        this.gpa = gpa;
    }

    @Override
    public String toString() {
        return "Student{" + name + ", iDNumber=" + iDNumber + ", gpa=" + gpa + "}";
    }
}
