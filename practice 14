import java.util.regex.Pattern;

public class Main {
    public static void main(String[] args) {
        // Задание 2
        String regex2 = "abcdefghijklmnopqrstuv18340";
        System.out.println("abcdefghijklmnopqrstuv18340".matches(regex2));
        System.out.println("abcdefghijklmnoasdfasdpqrstuv18340".matches(regex2));
        System.out.println("abcdefghijklmnopqrstuv18341".matches(regex2));

        // Задание 6
        String emailRegex =
            "^[a-zA-Z0-9.!#$%&'*+/=?^_`{|}~-]+" +
            "@[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?" +
            "(?:\\.[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?)*$";
        Pattern emailP = Pattern.compile(emailRegex);
        String[] emails = {
            "user@example.com", "root@localhost",
            "myhost@@com.ru", "@my.ru", "Julia String"
        };
        for (String e : emails) {
            System.out.println(e + " -> " + emailP.matcher(e).matches());
        }

        // Задание 7
        String passRegex = "^(?=.*[a-z])(?=.*[A-Z])(?=.*\\d)[a-zA-Z0-9_]{8,}$";
        Pattern passP = Pattern.compile(passRegex);
        String[] passwords = {"F032_Password", "TrySpy1", "smart_pass", "A007", "Password1"};
        for (String p : passwords) {
            System.out.println(p + " -> " + passP.matcher(p).matches());
        }
    }
}
