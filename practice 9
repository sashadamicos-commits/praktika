public class Main {
    public static void main(String[] args) {
        Student[] students = {
            new Student("Иванов", 3, 4.5),
            new Student("Петров", 1, 3.8),
            new Student("Сидоров", 2, 4.9),
            new Student("Кузнецов", 5, 4.1),
            new Student("Смирнов", 4, 5.0)
        };

        // Задание 1
        for (Student s : students) System.out.println(s);
        insertionSort(students);
        for (Student s : students) System.out.println(s);

        // Задание 2
        quickSortByGPA(students, 0, students.length - 1);
        for (Student s : students) System.out.println(s);
    }

    static void insertionSort(Student[] a) {
        for (int i = 1; i < a.length; i++) {
            Student key = a[i];
            int j = i - 1;
            while (j >= 0 && a[j].compareTo(key) > 0) {
                a[j + 1] = a[j];
                j--;
            }
            a[j + 1] = key;
        }
    }

    static void quickSortByGPA(Student[] a, int low, int high) {
        if (low < high) {
            int p = partition(a, low, high);
            quickSortByGPA(a, low, p - 1);
            quickSortByGPA(a, p + 1, high);
        }
    }

    static int partition(Student[] a, int low, int high) {
        double pivot = a[high].gpa;
        int i = low - 1;
        for (int j = low; j < high; j++) {
            if (a[j].gpa >= pivot) {
                i++;
                Student tmp = a[i]; a[i] = a[j]; a[j] = tmp;
            }
        }
        Student tmp = a[i + 1]; a[i + 1] = a[high]; a[high] = tmp;
        return i + 1;
    }
}

class Student implements Comparable<Student> {
    String name;
    int iDNumber;
    double gpa;

    Student(String name, int iDNumber, double gpa) {
        this.name = name;
        this.iDNumber = iDNumber;
        this.gpa = gpa;
    }

    @Override
    public int compareTo(Student o) {
        return Integer.compare(this.iDNumber, o.iDNumber);
    }

    @Override
    public String toString() {
        return "Student{" + name + ", iDNumber=" + iDNumber + ", gpa=" + gpa + "}";
    }
}
