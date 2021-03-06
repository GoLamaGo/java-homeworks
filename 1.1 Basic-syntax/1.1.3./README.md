## Задача 3. Аутентификация пользователя

### Описание
Большинство сайтов в Интернет и мобильных приложений требуют аутентификацию — это нужно не только, чтобы защитить личные данные, но и для того, чтобы иметь доступ к своим данным с любого устройства и подгружать данные по мере необходимости. Нашей задачей будет написать самый простой способ [аутентификации](https://ru.wikipedia.org/wiki/%D0%90%D1%83%D1%82%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F) — проверки введенных пользователем учетных данных, а именно: логина и пароля. 

### Функционал программы
- Вывод сообщения "Введите логин".
- Сохранение введенного значения в переменную login.
- Вывод сообщения "Введите пароль".
- Сохранение введенного значения в переменную password.
- Сравнение введенных значений с теми, что уже прописаны в программе:
  - если введенные логин и пароль совпали, то вывести сообщение: "Добро пожаловать, <Имя пользователя>!"
  - если введенные логин и пароль не совпали, то вывести сообщение: "Неверный логин или пароль!"
  (при проверке данных никогда не говорите, какие данные были введены неверно).
  
### Пример
Пример 1
```
Введите логин:
user1 <нажмите enter>
Введите пароль:
password1 <нажмите enter>
Неверный логин или пароль!
```
Пример 2
```
Введите логин:
admin <нажмите enter>
Введите пароль:
qwerty12345 <нажмите enter>
Добро пожаловать, admin!
```

### Реализация
1. Создадим новый repl на сайте [repl.it](https://repl.it/repls), как написано в инструкции к выполнению домашней работы, и зададим название `homework1.1.3`.

2. В файле `Main.java` написан следующий код:

```
class Main {
  public static void main(String[] args) {
    System.out.println("Hello world!");
  }
}
``` 

Весь код выполнения задачи нужно писать вместо `System.out.println("Hello world!");`:

```
  public static void main(String[] args) {
    System.out.println("Hello world!"); //Код сюда
  }
```

3. Нам нужно заранее создать логин и пароль, с которыми мы будем предоставлять доступ к данным и программе.
Должно получиться так:

```
  public static void main(String[] args) {
    String login = "admin";
    //Добавьте еще одну переменную с паролем, который будем проверять, пременную можно назвать password
  }
```

4. После добавления логина и пароля нужно вывести сообщение пользователю с просьбой ввода данных:

```
System.out.println("Измените сообщение для вывода его в консоли");
```

5. Чтобы читать сообщения из консоли, воспользуемся специальным объектом `Scanner` (на следующих лекциях
мы подробнее познакомимся с термином объект), описание `Scanner` (как ниже) делается только один раз на всю программу.

```
Scanner scanner = new Scanner(System.in);
``` 

6. Для того чтобы была возможность в коде использовать класс `Scanner`, нужно обязательно добавить `import` этого класса 
в самое начало файла `Main.java`:

```
import java.util.Scanner;
  
public static void main(String[] args) {
    //Код сюда
}
 ```

7. Чтобы прочитать и сохранить введенную строку из консоли, нужно написать:

```
String inputLogin = scanner.nextLine(); //Имя переменной можно придумать свое
```

8. Необходимо запросить ввод пароля сообщением в консоли:

```
System.out.println("Измените сообщение для вывода его в консоли");
```

9. С помощью оператора `if else` проверить, совпадают ли логин и пароль, введенные из консоли, с теми, что мы описали в начале программы:

```
if (login.equals(inputLogin) && password.equals(inputPassword)) {
    //Вывести сообщение в консоль
} else {
  //Вывести сообщение в консоль
}
```

10. Завершить работу программы.
