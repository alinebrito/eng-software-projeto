# LAB: Revisando Conceitos Básicos de Projeto de Software - Refatoração & Compreensão de Código


# Refatoração & Compreensão de Código


1. Um desenvolvedor realizou  refatorações no método [public NetServerOptions(JsonObject)](https://github.com/eclipse-vertx/vert.x/commit/0ef66582ffaba9a8df1cad846880df2074d34505#diff-da89f354a3ce2d410a9f9af22a3d7343b813f426f3187235148bfef8adc96088L87) da classe `NetServerOptions` do projeto `eclipse-vertx`. Inspecione o código e identifique quais foram as operações realizada. 
Após identificar as refatorações, compare os seus resultados com [o gabarito](https://github.com/alinebrito/composite-refactoring-catalog/blob/main/results/oracle/eclipse/vert.x/results/decomposition_extract_method/view/subgraph_atomic_5.md). Discuta sobre os desafios de visualizar mudanças em códigos com refatorações utilizando o "diff" do GitHub. 

2. Um desenvolvedor realizou  refatorações nas classes `Maven30ServerEmbedderImpl`, `Maven3ServerEmbedder`, e `Maven32ServerEmbedderImpl` em um [commit](https://github.com/JetBrains/intellij-community/commit/6ff3fe00d7ffe04dbe0904b8bad98285b6988d6d) do projeto JetBrains. Inspecione o código e identifique quais foram as operações realizada. Após identificar as refatorações, compare os seus resultados com [o gabarito](https://github.com/alinebrito/composite-refactoring-catalog/blob/main/results/oracle/JetBrains/intellij-community/results/composition_pull_up_method/view/subgraph_atomic_0.md). Discuta sobre os desafios de visualizar mudanças em códigos com refatorações utilizando o "diff" do GitHub. 

# Princípio de Demeter

O Princípio de Demeter defende que um método deve invocar apenas métodos:

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
- Capítulo 9 - Refactoring
