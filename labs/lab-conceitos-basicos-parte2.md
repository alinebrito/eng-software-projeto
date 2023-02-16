# LAB: Revisando Conceitos Básicos de Projeto de Software - Independência Funcional,  Refatoração e Princípio de Demeter

# Independência Funcional

Atingimos a independência funcional desenvolvendo módulos com função única e com aversão a interação excessiva. Por que devemos nos esforçar para criar módulos independentes? Pense e discuta as vantagens de respeitar este princípio.

# Refatoração: Extract Method

Refactorings são transformações de código, visando, por exemplo, melhorar a manutenibilidade de um sistema.

Observe os trechos de código a seguir. Para cada um deles, extraia o código comentado com a palavra "extrair" para novo método.

a) 

```java
class A {
  void f() {
    int x = 10
    x++;      
    print x;   // extrair
  }
}
```

b) 

```java
class A {
  void f() {
    int x = 10
    x++;     // extrair
    print x; // extrair
  }
}
```

c)

```java
class A {
  void f() {
    int x = 10
    x++;     // extrair
    print x; // extrair
    int y = x+1;
    ...
  }
}
```

d)

```java
class A {
  void f() {
    int x = 10
    int y;     // extrair
    y = h()*2; // extrair
    print y;   // extrair
    int z = y+1;
    ...
  }
}
```

# Princípio de Demeter

O Princípio de Demeter defende que um método deve invovar apenas métodos:

* de sua própria classe (caso 1)

* de objetos passados como parâmetros (caso 2)

* de objetos criados pelo próprio método (caso 3)

* de atributos da classe do método (caso 4)

Observe o código abaixo e idenfique cada caso, assim como, o trecho que viola este princípio.

```java
class PrincipioDemeter {

  T1 attr;

  void f1() { 
    ...
  }

  void m1(T2 p) {  // método que segue Demeter
    f1();           // caso 1: própria classe
    p.f2();         // caso 2: parâmetro
    new T3().f3();  // caso 3: criado pelo método
    attr.f4();      // caso 4: atributo da classe
  }

  void m2(T4 p) {  // método que viola Demeter
    p.getX().getY().getZ().doSomething();
  }

}
```

# Referências

Engenharia de Software - Uma abordagem Profissional. 8ª ed. Roger Pressman, Bruce Maxim. 
- Capítulo 12.3 - Conceitos de Projeto. 


[Engenharia de Software Moderna](https://engsoftmoderna.info). Marco Tulio Valente. 
- Capítulo 9 - Refactoring
- Capítulo 5.6.5 Princípio de Demeter