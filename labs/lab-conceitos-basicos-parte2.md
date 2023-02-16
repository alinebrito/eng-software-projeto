# LAB: Revisando Conceitos Básicos de Projeto de Software - Parte 2

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


# Referências

Engenharia de Software - Uma abordagem Profissional. 8ª ed. Roger Pressman, Bruce Maxim. 
- Capítulo 12.3 - Conceitos de Projeto. 

[Engenharia de Software Moderna](https://engsoftmoderna.info). Marco Tulio Valente. 
- Capítulo 9 - Refactoring
