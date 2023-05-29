Versão inicial:

```java
class Logger {

  public void println(String msg) {
    // registra msg no console, mas poderia ser em arquivo
    System.out.println(msg);
  }
}

class Main {

  void f() {
    Logger log = new Logger();  
    log.println("Executando f" + log);
  }

  void g() {
    Logger log = new Logger();
    log.println("Executando g " + log);
  }

  void h() {
    Logger log = new Logger();  
    log.println("Executando h " + log);
  }
  
  public static void main(String[] args) {
    Main main = new Main();
    main.f();
    main.g();
    main.h();
  }
}
```

Versão após mudanças:

```java
class Logger {

  private Logger() {} // proíbe clientes chamar new Logger()

  private static Logger instance; // instância única

  public static Logger getInstance() {
    if (instance == null) // 1a vez que chama-se getInstance
      instance = new Logger();
    return instance;
  }

  public void println(String msg) {
    // registra msg no console, mas poderia ser em arquivo
    System.out.println(msg);
  }
}


void f() {
  Logger log = Logger.getInstance();
  log.println("Executando f");
  ...
}

void g() {
  Logger log = Logger.getInstance();
  log.println("Executando g");
  ...
}

void h() {
  Logger log = Logger.getInstance();
  log.println("Executando h");
  ...
}
```