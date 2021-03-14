**������� ��������**

14.03.2021 ���� ��������� �������������� ������������ ���������� Credit Card Number Validator.

�� ������������ ���������: 1 ���

� ���������� ������������ �������� �������� �� ����

**�������� �������� ������������**

� �������� ������������ �������������� ��������� ���������:

1. [����������� �� ��������� IntelliJ IDEA](https://github.com/netology-code/javaqa-homeworks/blob/master/intro/idea.md)
2. [��������� ������� ��������� ����](https://www.getcreditcardnumbers.com/)
3. [�������� ������� � ������� �1.1. �������� � Java: JDK, JRE, JVM, IntelliJ IDEA�](https://github.com/netology-code/javaqa-homeworks/tree/master/intro)

� �������� �������� ������ ������������� ������ � [�������� �������](https://github.com/netology-code/javaqa-homeworks/tree/master/intro) ���:

public class Main {
  public static void main(String[] args) {
    // TODO: ����������� ����� ����� ����� ���� ����� �������� ���������, ��� ��������
    String number = "5351719427810741";
    System.out.println(String.format("Result is %s", isValidCardNumber(number) ? "OK" : "FAIL"));
  }

  public static boolean isValidCardNumber(String number) {
    if (number == null) {
      return false;
    }

    if (number.length() != 16) {
      return false;
    }

    long result = 0;
    for (int i = 0; i < number.length(); i++) {
      int digit;
      try {
        digit = Integer.parseInt(number.charAt(i) + "");
      } catch (NumberFormatException e) {
        return false;
      }

      if (i % 2 == 0) {
        digit *= 2;
        if (digit > 9) {
          digit -= 9;
        }
      }
      result += digit;
    }

    return (result != 0) && (result % 10 == 0);
  }
}

������������ ������������� � ��������� ���������:

Windows 8.1 x64
Java 11
Git 2.30.2