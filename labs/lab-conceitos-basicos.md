# LAB: Revisando Conceitos Básicos de Projeto de Software (Parte 1)

# Abstração

> "Abstração é uma das maneiras fundamentais como nós, seres humanos, lidamos com a complexidade." - Grady Booch

Segundo Pressman, uma **abstração procedural** "refere-se a uma sequência de instruções que possuem uma função específica e limitada". Por exemplo, a palavra "Abrir" para uma porta, que inclui uma longa lista de sequências procedurais. Por exemplo, para uma porta comum, a sequência inclui dirigir-se até a porta, alcançar e agarrar a maçaneta, girar a maçaneta, puxar a porta, afastar-se da porta em movimento, etc. Pense e lista as etapas necessárias para abrir um portão automático. Observe que a função implicada permanece a mesma (isto é, "abrir"), porém o conjunto de operações é substituído.


# Ocultamento de Informações

Suponha que a classe abaixo seja utilizada em um sistema de estacionamentos. Esta classe não oculta estruturas que podem mudar no futuro. Reescreva este código, visando encapsular a estrutura de dados responsável por armazenar veículos, isto é, a tabela hash.

```java
import java.util.Hashtable;

public class Estacionamento {

  public Hashtable<String, String> veiculos;

  public Estacionamento() {
    veiculos = new Hashtable<String, String>();
  }

  public static void main(String[] args) {
    Estacionamento e = new Estacionamento();
    e.veiculos.put("TCP-7030", "Uno");
    e.veiculos.put("BNF-4501", "Gol");
    e.veiculos.put("JKL-3481", "Corsa");
  }
}
```

# Separação de Interesses

Separação de interesses é uma propriedade importante, que defende uma classe deve ter apenas um interesse (isto é, funcionalidade, requisito ou responsabilidade). Recomendações:

* Uma classe deve ter uma única responsabilidade

* Uma classe deve implementar um único interesse

* Uma classe deve ser coesa, ou seja, deve implementar uma única funcionalidade ou serviço.

Observe esta nova versão da classe Estacionamento, que inclui  também informações sobre o gerente. Quais são as responsabilidades desta classe? Você realizaria alguma mudança? Se sim, reescreva a classe visando esta melhoria.

```java
class Estacionamento {
  ...
  private String nome_gerente;
  private String fone_gerente;
  private String cpf_gerente;
  private String endereco_gerente;
  private Hashtable<String, String> veiculos;
  ..

}  
```

# Coesão

A função abaixo possui um problema de coesão, isto é, ele implementa mais de uma funcionalidade. Como você resolveria este problema?

```java
float sin_or_cos(double x, int op) {
  if (op == 1)
    "calcula e retorna seno de x"
  else
    "calcula e retorna cosseno de x"
}
```

# Independência Funcional

Atingimos a independência funcional desenvolvendo módulos com função única e com aversão a interação excessiva. Por que devemos nos esforçar para criar módulos independentes? Pense e discuta as vantagens de respeitar este princípio.


## Referências

Engenharia de Software - Uma abordagem Profissional. 8ª ed. Roger Pressman, Bruce Maxim. 
- Capítulo 12.3 - Conceitos de Projeto. 
- Capítulo 16 - Projeto Baseado em Padrões


[Engenharia de Software Moderna](https://engsoftmoderna.info). Marco Tulio Valente. 
- Capítulo 6 - Padrões de Projeto
- Capítulo 5.3 - Ocultamento de Informação
- Capítulo 9 - Refactoring



