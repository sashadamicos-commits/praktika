import java.util.*;

public class Main {
    public static void main(String[] args) {
        // Задание 1
        Student testStudent = new Student("Тестов", 0, 4.0);
        System.out.println(testStudent);

        // Задание 2
        SortingStudentsByGPA sorter = new SortingStudentsByGPA();
        sorter.setArray();
        sorter.outArray("Исходный массив");

        sorter.quickSort(0, sorter.iDNumber.size() - 1);
        sorter.outArray("После быстрой сортировки (по GPA, убывание)");

        sorter.mergeSort(0, sorter.iDNumber.size() - 1);
        sorter.outArray("После сортировки слиянием (по GPA, убывание)");

        sorter.sortByField("name");
        sorter.outArray("После сортировки по имени");

        // Задание 3
        SortingStudentsByGPA s1 = new SortingStudentsByGPA();
        s1.iDNumber = new ArrayList<>(List.of(
            new Student("Иванов", 1, 4.0),
            new Student("Петров", 3, 3.5),
            new Student("Сидоров", 5, 4.8)
        ));

        SortingStudentsByGPA s2 = new SortingStudentsByGPA();
        s2.iDNumber = new ArrayList<>(List.of(
            new Student("Кузнецов", 2, 4.5),
            new Student("Смирнов", 4, 4.1)
        ));

        SortingStudentsByGPA merged = SortingStudentsByGPA.mergeTwoLists(s1, s2);
        merged.outArray("Объединённый отсортированный список");
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

class SortingStudentsByGPA {
    ArrayList<Student> iDNumber = new ArrayList<>();

    Comparator<Student> byGpaDesc = (a, b) -> Double.compare(b.gpa, a.gpa);

    void setArray() {
        iDNumber.add(new Student("Иванов", 3, 4.5));
        iDNumber.add(new Student("Петров", 1, 3.8));
        iDNumber.add(new Student("Сидоров", 2, 4.9));
        iDNumber.add(new Student("Кузнецов", 5, 4.1));
        iDNumber.add(new Student("Смирнов", 4, 5.0));
    }

    void quickSort(int low, int high) {
        if (low < high) {
            int p = partition(low, high);
            quickSort(low, p - 1);
            quickSort(p + 1, high);
        }
    }

    int partition(int low, int high) {
        Student pivot = iDNumber.get(high);
        int i = low - 1;
        for (int j = low; j < high; j++) {
            if (byGpaDesc.compare(iDNumber.get(j), pivot) <= 0) {
                i++;
                Collections.swap(iDNumber, i, j);
            }
        }
        Collections.swap(iDNumber, i + 1, high);
        return i + 1;
    }

    void mergeSort(int low, int high) {
        if (low < high) {
            int mid = (low + high) / 2;
            mergeSort(low, mid);
            mergeSort(mid + 1, high);
            merge(low, mid, high);
        }
    }

    void merge(int low, int mid, int high) {
        ArrayList<Student> left = new ArrayList<>(iDNumber.subList(low, mid + 1));
        ArrayList<Student> right = new ArrayList<>(iDNumber.subList(mid + 1, high + 1));
        int i = 0, j = 0, k = low;
        while (i < left.size() && j < right.size()) {
            if (byGpaDesc.compare(left.get(i), right.get(j)) <= 0) {
                iDNumber.set(k++, left.get(i++));
            } else {
                iDNumber.set(k++, right.get(j++));
            }
        }
        while (i < left.size()) iDNumber.set(k++, left.get(i++));
        while (j < right.size()) iDNumber.set(k++, right.get(j++));
    }

    void sortByField(String field) {
        if ("name".equals(field)) iDNumber.sort(Comparator.comparing(s -> s.name));
        else if ("id".equals(field)) iDNumber.sort(Comparator.comparingInt(s -> s.iDNumber));
        else if ("gpa".equals(field)) iDNumber.sort(byGpaDesc);
    }

    void outArray(String title) {
        System.out.println(title);
        for (Student s : iDNumber) System.out.println(s);
    }

    static SortingStudentsByGPA mergeTwoLists(SortingStudentsByGPA a, SortingStudentsByGPA b) {
        SortingStudentsByGPA result = new SortingStudentsByGPA();
        result.iDNumber.addAll(a.iDNumber);
        result.iDNumber.addAll(b.iDNumber);
        result.iDNumber.sort(Comparator.comparingInt(s -> s.iDNumber));
        return result;
    }
}
