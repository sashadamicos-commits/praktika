import java.text.SimpleDateFormat;
import java.util.*;

public class Main {
    public static void main(String[] args) throws Exception {
        // Задание 1
        Date received = new Date();
        System.out.println("Фамилия: Иванов");
        System.out.println("Получено: " + new SimpleDateFormat("dd.MM.yyyy HH:mm:ss").format(received));
        System.out.println("Сдано: " + new SimpleDateFormat("dd.MM.yyyy HH:mm:ss")
                .format(new Date(System.currentTimeMillis())));

        // Задание 2
        SimpleDateFormat sdf = new SimpleDateFormat("dd.MM.yyyy");
        Date userDate = sdf.parse("01.01.2020");
        Date now = new Date();
        System.out.println("Пользовательская дата: " + sdf.format(userDate));
        System.out.println("Текущая дата: " + sdf.format(now));
        if (userDate.before(now)) System.out.println("Пользовательская дата в прошлом");
        else if (userDate.after(now)) System.out.println("Пользовательская дата в будущем");
        else System.out.println("Даты совпадают");

        // Задание 3
        Calendar bd = new GregorianCalendar(2000, Calendar.MAY, 15);
        Student st = new Student("Иванов", bd.getTime());
        System.out.println(st);
        System.out.println("Короткий: " + st.getBirthDate("short"));
        System.out.println("Средний: " + st.getBirthDate("medium"));
        System.out.println("Полный: " + st.getBirthDate("full"));

        // Задание 4
        int y = 2024, m = 3, d = 15, h = 14, min = 30;
        Calendar cal = new GregorianCalendar(y, m - 1, d, h, min);
        Date dateFromCal = cal.getTime();
        Date dateFromMillis = new Date(cal.getTimeInMillis());
        SimpleDateFormat fmt = new SimpleDateFormat("dd.MM.yyyy HH:mm");
        System.out.println("Ввод: " + y + "-" + m + "-" + d + " " + h + ":" + min);
        System.out.println("Calendar -> Date: " + fmt.format(dateFromCal));
        System.out.println("Date (из millis): " + fmt.format(dateFromMillis));

        // Задание 5
        compareListPerformance();
    }

    static void compareListPerformance() {
        int N = 100_000;

        ArrayList<Integer> arr = new ArrayList<>();
        LinkedList<Integer> link = new LinkedList<>();

        long t = System.nanoTime();
        for (int i = 0; i < N; i++) arr.add(i);
        System.out.println("ArrayList add:    " + (System.nanoTime() - t) / 1_000_000 + " ms");

        t = System.nanoTime();
        for (int i = 0; i < N; i++) link.add(i);
        System.out.println("LinkedList add:   " + (System.nanoTime() - t) / 1_000_000 + " ms");

        t = System.nanoTime();
        for (int i = 0; i < N; i++) arr.get(i);
        System.out.println("ArrayList get:    " + (System.nanoTime() - t) / 1_000_000 + " ms");

        t = System.nanoTime();
        for (int i = 0; i < N; i++) link.get(i);
        System.out.println("LinkedList get:   " + (System.nanoTime() - t) / 1_000_000 + " ms");

        int small = 1000;
        t = System.nanoTime();
        for (int i = 0; i < small; i++) arr.remove(0);
        System.out.println("ArrayList remove: " + (System.nanoTime() - t) / 1_000_000 + " ms");

        t = System.nanoTime();
        for (int i = 0; i < small; i++) link.remove(0);
        System.out.println("LinkedList remove:" + (System.nanoTime() - t) / 1_000_000 + " ms");

        t = System.nanoTime();
        for (int i = 0; i < N; i++) arr.contains(i);
        System.out.println("ArrayList search: " + (System.nanoTime() - t) / 1_000_000 + " ms");

        t = System.nanoTime();
        for (int i = 0; i < N; i++) link.contains(i);
        System.out.println("LinkedList search:" + (System.nanoTime() - t) / 1_000_000 + " ms");
    }
}

class Student {
    String name;
    Date birthDate;

    Student(String name, Date birthDate) {
        this.name = name;
        this.birthDate = birthDate;
    }

    String getBirthDate(String format) {
        SimpleDateFormat sdf;
        switch (format) {
            case "short":  sdf = new SimpleDateFormat("dd.MM.yy"); break;
            case "medium": sdf = new SimpleDateFormat("dd MMM yyyy"); break;
            case "full":   sdf = new SimpleDateFormat("EEEE, dd MMMM yyyy"); break;
            default:       sdf = new SimpleDateFormat("dd.MM.yyyy");
        }
        return sdf.format(birthDate);
    }

    @Override
    public String toString() {
        return "Student{" + name + ", birthDate="
                + new SimpleDateFormat("dd.MM.yyyy").format(birthDate) + "}";
    }
}
