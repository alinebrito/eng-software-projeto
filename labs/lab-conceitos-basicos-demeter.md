# Princípio de Demeter

O Princípio de Demeter defende que um método deve invocar apenas métodos:

* de sua própria classe (caso 1)

* de objetos passados como parâmetros (caso 2)

* de objetos criados pelo próprio método (caso 3)

* de atributos da classe do método (caso 4)

Observe o código abaixo, extraído do Livro de Engenharia de Software Moderna. Identifique cada caso, assim como, o trecho que viola este princípio.

```java
class PrincipioDemeter {

  T1 attr;

  void f1() { 
    ...
  }

  void m1(T2 p) {
    f1();           
    p.f2();        
    new T3().f3();  
    attr.f4();      
  }

  void m2(T4 p) {
    p.getX().getY().getZ().doSomething();
  }

}
```

# Referências

[1] Engenharia de Software - Uma abordagem Profissional. 8ª ed. Roger Pressman, Bruce Maxim. 
- Capítulo 12.3 - Conceitos de Projeto. 

[2] [Engenharia de Software Moderna](https://engsoftmoderna.info). Marco Tulio Valente. 
- Capítulo 5 - Princípios de Projeto