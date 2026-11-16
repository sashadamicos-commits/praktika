//задание 1
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        SingleLinkedList list = new SingleLinkedList();
        int choice;

        do {
            System.out.println("\n--- МЕНЮ (Односвязный список) ---");
            System.out.println("1. Добавить студента");
            System.out.println("2. Удалить студента по имени");
            System.out.println("3. Вывести всех студентов");
            System.out.println("4. Очистить список");
            System.out.println("5. Проверить на пустоту");
            System.out.println("0. Выход");
            System.out.print("Выбор: ");
            choice = sc.nextInt();
            sc.nextLine();

            switch (choice) {
                case 1:
                    System.out.print("Имя: ");
                    String name = sc.nextLine();
                    System.out.print("Возраст: ");
                    int age = sc.nextInt();
                    sc.nextLine();
                    list.add(new Student(name, age));
                    System.out.println("Студент добавлен.");
                    break;
                case 2:
                    System.out.print("Имя для удаления: ");
                    String delName = sc.nextLine();
                    list.remove(delName);
                    break;
                case 3:
                    list.print();
                    break;
                case 4:
                    list.clear();
                    System.out.println("Список очищен.");
                    break;
                case 5:
                    System.out.println("Список пуст? " + list.isEmpty());
                    break;
                case 0:
                    System.out.println("Выход...");
                    break;
                default:
                    System.out.println("Неверный выбор.");
            }
        } while (choice != 0);

        sc.close();
    }
}

class Student {
    String name;
    int age;

    Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    void print() {
        System.out.println("Студент: " + name + ", Возраст: " + age);
    }
}

class SingleNode {
    Student data;
    SingleNode next;

    SingleNode(Student data) {
        this.data = data;
        this.next = null;
    }
}

class SingleLinkedList {
    private SingleNode head;

    SingleLinkedList() {
        head = null;
    }

    boolean isEmpty() {
        return head == null;
    }

    void add(Student s) {
        SingleNode newNode = new SingleNode(s);
        if (head == null) {
            head = newNode;
        } else {
            SingleNode current = head;
            while (current.next != null) {
                current = current.next;
            }
            current.next = newNode;
        }
    }

    void remove(String name) {
        if (head == null) return;
        if (head.data.name.equals(name)) {
            head = head.next;
            return;
        }
        SingleNode current = head;
        while (current.next != null && !current.next.data.name.equals(name)) {
            current = current.next;
        }
        if (current.next != null) {
            current.next = current.next.next;
        }
    }

    void print() {
        if (isEmpty()) {
            System.out.println("Список пуст.");
            return;
        }
        SingleNode current = head;
        while (current != null) {
            current.data.print();
            current = current.next;
        }
    }

    void clear() {
        head = null;
    }
}


//Задание 2

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        DoubleLinkedList doubleList = new DoubleLinkedList();
        CircularLinkedList circularList = new CircularLinkedList();
        int structureChoice;

        System.out.println("Выберите структуру данных для работы:");
        System.out.println("1 - Двухсвязный список");
        System.out.println("2 - Кольцевой список");
        System.out.print("Выбор: ");
        structureChoice = sc.nextInt();

        int choice;
        do {
            System.out.println("\n--- МЕНЮ ---");
            System.out.println("1. Добавить студента");
            System.out.println("2. Удалить студента по имени");
            System.out.println("3. Вывести всех студентов");
            System.out.println("4. Очистить список");
            System.out.println("5. Проверить на пустоту");
            System.out.println("0. Выход");
            System.out.print("Выбор: ");
            choice = sc.nextInt();
            sc.nextLine();

            switch (choice) {
                case 1:
                    System.out.print("Имя: ");
                    String name = sc.nextLine();
                    System.out.print("Возраст: ");
                    int age = sc.nextInt();
                    sc.nextLine();
                    Student s = new Student(name, age);
                    if (structureChoice == 1) doubleList.add(s);
                    else circularList.add(s);
                    System.out.println("Студент добавлен.");
                    break;
                case 2:
                    System.out.print("Имя для удаления: ");
                    String delName = sc.nextLine();
                    if (structureChoice == 1) doubleList.remove(delName);
                    else circularList.remove(delName);
                    break;
                case 3:
                    if (structureChoice == 1) doubleList.print();
                    else circularList.print();
                    break;
                case 4:
                    if (structureChoice == 1) doubleList.clear();
                    else circularList.clear();
                    System.out.println("Список очищен.");
                    break;
                case 5:
                    boolean empty = (structureChoice == 1) ? doubleList.isEmpty() : circularList.isEmpty();
                    System.out.println("Список пуст? " + empty);
                    break;
                case 0:
                    System.out.println("Выход...");
                    break;
                default:
                    System.out.println("Неверный выбор.");
            }
        } while (choice != 0);

        sc.close();
    }
}

class Student {
    String name;
    int age;

    Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    void print() {
        System.out.println("Студент: " + name + ", Возраст: " + age);
    }
}

class DoubleNode {
    Student data;
    DoubleNode prev;
    DoubleNode next;

    DoubleNode(Student data) {
        this.data = data;
        this.prev = null;
        this.next = null;
    }
}

class DoubleLinkedList {
    private DoubleNode head;
    private DoubleNode tail;

    DoubleLinkedList() {
        head = null;
        tail = null;
    }

    boolean isEmpty() {
        return head == null;
    }

    void add(Student s) {
        DoubleNode newNode = new DoubleNode(s);
        if (head == null) {
            head = newNode;
            tail = newNode;
        } else {
            tail.next = newNode;
            newNode.prev = tail;
            tail = newNode;
        }
    }

    void remove(String name) {
        if (head == null) return;
        DoubleNode current = head;
        while (current != null && !current.data.name.equals(name)) {
            current = current.next;
        }
        if (current == null) return;

        if (current.prev != null) {
            current.prev.next = current.next;
        } else {
            head = current.next;
        }
        if (current.next != null) {
            current.next.prev = current.prev;
        } else {
            tail = current.prev;
        }
    }

    void print() {
        if (isEmpty()) {
            System.out.println("Список пуст.");
            return;
        }
        DoubleNode current = head;
        while (current != null) {
            current.data.print();
            current = current.next;
        }
    }

    void clear() {
        head = null;
        tail = null;
    }
}

class CircularNode {
    Student data;
    CircularNode next;

    CircularNode(Student data) {
        this.data = data;
        this.next = null;
    }
}

class CircularLinkedList {
    private CircularNode head;

    CircularLinkedList() {
        head = null;
    }

    boolean isEmpty() {
        return head == null;
    }

    void add(Student s) {
        CircularNode newNode = new CircularNode(s);
        if (head == null) {
            head = newNode;
            head.next = head;
        } else {
            CircularNode current = head;
            while (current.next != head) {
                current = current.next;
            }
            current.next = newNode;
            newNode.next = head;
        }
    }

    void remove(String name) {
        if (head == null) return;
        if (head.data.name.equals(name) && head.next == head) {
            head = null;
            return;
        }
        if (head.data.name.equals(name)) {
            CircularNode current = head;
            while (current.next != head) {
                current = current.next;
            }
            head = head.next;
            current.next = head;
            return;
        }
        CircularNode current = head;
        while (current.next != head && !current.next.data.name.equals(name)) {
            current = current.next;
        }
        if (current.next != head) {
            current.next = current.next.next;
        }
    }

    void print() {
        if (isEmpty()) {
            System.out.println("Список пуст.");
            return;
        }
        CircularNode current = head;
        do {
            current.data.print();
            current = current.next;
        } while (current != head);
    }

    void clear() {
        head = null;
    }
}
