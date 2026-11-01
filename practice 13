import java.util.*;

public class Main {
    public static void main(String[] args) {
        // Задание 1
        processString("I like Java!!!");

        // Задание 2
        System.out.println(new Person("Иванов", "Иван", "Иванович").getFullName());
        System.out.println(new Person("Петров", null, null).getFullName());
        System.out.println(new Person("Сидоров", "Сергей", null).getFullName());

        // Задание 3
        String addr = "Россия, Московская область, Москва, Тверская, 10, 2, 45";
        System.out.println(Address.parseSplit(addr));
        System.out.println(Address.parseTokenizer(addr));

        // Задание 4
        String[] shirts = {
            "S001,Black Polo Shirt,Black,XL",
            "S002,Black Polo Shirt,Black,L",
            "S003,Blue Polo Shirt,Blue,XL",
            "S004,Blue Polo Shirt,Blue,M",
            "S005,Tan Polo Shirt,Tan,XL",
            "S006,Black T-Shirt,Black,XL",
            "S007,White T-Shirt,White,XL",
            "S008,White T-Shirt,White,L",
            "S009,Green T-Shirt,Green,S",
            "S010,Orange T-Shirt,Orange,S",
            "S011,Maroon Polo Shirt,Maroon,S"
        };
        Shirt[] shirtObjs = new Shirt[shirts.length];
        for (int i = 0; i < shirts.length; i++) shirtObjs[i] = Shirt.parse(shirts[i]);
        for (Shirt sh : shirtObjs) System.out.println(sh);

        // Задание 5
        System.out.println(PhoneFormatter.format("+79175655655"));
        System.out.println(PhoneFormatter.format("+104289652211"));
        System.out.println(PhoneFormatter.format("89175655655"));

        // Задание 6
        List<String> words = Arrays.asList("абв", "где", "вага", "еж", "жи");
        System.out.println(buildChain(words));
    }

    static void processString(String s) {
        System.out.println(s);
        System.out.println(s.charAt(s.length() - 1));
        System.out.println(s.endsWith("!!!"));
        System.out.println(s.startsWith("I like"));
        System.out.println(s.contains("Java"));
        System.out.println(s.indexOf("Java"));
        System.out.println(s.replace('a', 'o'));
        System.out.println(s.toUpperCase());
        System.out.println(s.toLowerCase());
        int start = s.indexOf("Java");
        System.out.println(s.substring(0, start) + s.substring(start + 4));
    }

    static String buildChain(List<String> words) {
        List<String> remaining = new ArrayList<>(words);
        if (remaining.isEmpty()) return "";
        StringBuilder sb = new StringBuilder();
        String current = remaining.remove(0);
        sb.append(current);
        boolean progress = true;
        while (progress && !remaining.isEmpty()) {
            progress = false;
            char last = Character.toLowerCase(current.charAt(current.length() - 1));
            for (int i = 0; i < remaining.size(); i++) {
                String w = remaining.get(i);
                if (Character.toLowerCase(w.charAt(0)) == last) {
                    sb.append(" -> ").append(w);
                    current = w;
                    remaining.remove(i);
                    progress = true;
                    break;
                }
            }
        }
        return sb.toString();
    }
}

class Person {
    private String lastName, firstName, middleName;

    Person(String lastName, String firstName, String middleName) {
        this.lastName = lastName;
        this.firstName = firstName;
        this.middleName = middleName;
    }

    String getFullName() {
        StringBuilder sb = new StringBuilder(lastName);
        if (firstName != null) sb.append(" ").append(firstName.charAt(0)).append(".");
        if (middleName != null) sb.append(" ").append(middleName.charAt(0)).append(".");
        return sb.toString();
    }
}

class Address {
    String country, region, city, street, house, building, apartment;

    static Address parseSplit(String s) {
        String[] p = s.split(",\\s*");
        Address a = new Address();
        a.country = p[0];
        a.region = p[1];
        a.city = p[2];
        a.street = p[3];
        a.house = p[4];
        a.building = p[5];
        a.apartment = p[6];
        return a;
    }

    static Address parseTokenizer(String s) {
        StringTokenizer st = new StringTokenizer(s, ",");
        Address a = new Address();
        a.country = st.nextToken().trim();
        a.region = st.nextToken().trim();
        a.city = st.nextToken().trim();
        a.street = st.nextToken().trim();
        a.house = st.nextToken().trim();
        a.building = st.nextToken().trim();
        a.apartment = st.nextToken().trim();
        return a;
    }

    @Override
    public String toString() {
        return "Address{" + country + ", " + region + ", " + city + ", " + street
                + ", " + house + ", " + building + ", " + apartment + "}";
    }
}

class Shirt {
    String id, name, color, size;

    static Shirt parse(String s) {
        String[] p = s.split(",");
        Shirt sh = new Shirt();
        sh.id = p[0];
        sh.name = p[1];
        sh.color = p[2];
        sh.size = p[3];
        return sh;
    }

    @Override
    public String toString() {
        return "Shirt{id=" + id + ", name=" + name + ", color=" + color + ", size=" + size + "}";
    }
}

class PhoneFormatter {
    static String format(String s) {
        String digits;
        if (s.startsWith("+")) {
            digits = s.substring(1);
        } else if (s.startsWith("8") && s.length() == 11) {
            digits = "7" + s.substring(1);
        } else {
            return "Неверный формат";
        }
        if (digits.length() < 11) return "Неверный формат";
        String country = digits.substring(0, digits.length() - 10);
        String rest = digits.substring(digits.length() - 10);
        return "+" + country + " " + rest.substring(0, 3) + " "
                + rest.substring(3, 6) + " " + rest.substring(6);
    }
}
