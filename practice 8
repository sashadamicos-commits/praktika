public class Main {
    public static void main(String[] args) {
        // Задание 6
        for (int n : new int[]{2, 3, 4, 17, 18, 97, 100}) {
            System.out.println(n + " -> " + (isPrime(n, 2) ? "YES" : "NO"));
        }

        // Задание 7
        System.out.print("360 = ");
        factorize(360);
        System.out.println();
        System.out.print("97 = ");
        factorize(97);
        System.out.println();
        System.out.print("1001 = ");
        factorize(1001);
        System.out.println();

        // Задание 8
        for (String s : new String[]{"шалаш", "abba", "hello", "a"}) {
            System.out.println(s + " -> " + (isPalindrome(s) ? "YES" : "NO"));
        }
    }

    static boolean isPrime(int n, int divisor) {
        if (n < 2) return false;
        if (divisor * divisor > n) return true;
        if (n % divisor == 0) return false;
        return isPrime(n, divisor + 1);
    }

    static void factorize(int n) {
        factorizeHelper(n, 2);
    }

    static void factorizeHelper(int n, int d) {
        if (n == 1) return;
        if (n % d == 0) {
            System.out.print(d + " ");
            factorizeHelper(n / d, d);
        } else {
            factorizeHelper(n, d + 1);
        }
    }

    static boolean isPalindrome(String s) {
        return isPalindromeHelper(s, 0, s.length() - 1);
    }

    static boolean isPalindromeHelper(String s, int left, int right) {
        if (left >= right) return true;
        if (s.charAt(left) != s.charAt(right)) return false;
        return isPalindromeHelper(s, left + 1, right - 1);
    }
}
