# LAB: Padrões de Projeto

Para realizar este laboratório prático, você precisar criar uma conta na plataforma [replit](https://replit.com/).

## Polimorfismo

_General Responsability Assignment Software Patterns_ (GRASP) descrevem princípios fundamentais de projeto baseado em objetos e atribuição de responsabilidades aos mesmos.

Polimorfismo é um dos princípios documentados. A ideia consiste em "atribuir as responsabilidades pelos comportamentos aos tipos para qual o comportamento varia, usando operações polimórficas" (Larman).


O [exemplo 1](https://replit.com/@anbrito/BancoImobiliario) mostra um "projeto ruim" que poderia se beneficiar deste padrão. Neste caso, temos parte de um código de um jogo de Banco Imobiliário. Existe um lucro ou o pagamento de uma taxa conforme a casa atingida pelo jogador no tabuleiro, utilizando uma estrutura de switch/case. Dessa forma, o código testa o tipo de casa para aplicar a regra.

Atualize o código considerando Polimorfismo. Basicamente, você deve criar uma classe abstrata "Casa" e cada subtipo será uma classe distinta com a respectiva operação.

## Singleton

O [exemplo 2](https://replit.com/@anbrito/LoggerSingleton) mostra uma exemplo de projeto com uma classe Logger, que basicamente registra as operações realizadas no sistema.

Como podemos observar, cada método cria sua própria instância de Logger.

Transforme a classe Logger em Singleton, para que exista apenas uma única instância dessa classe no projeto.

Para editar o projeto, basta criar um _fork_.


## Referências

Marco Tulio Valente. Engenharia de Software Moderna: Princípios e Práticas para Desenvolvimento de Software com Produtividade. 2020. Capítulo 6.3  - Singleton

Utilizando UML e Padrões: Uma Introdução à Análise e ao Projeto Orientados a Objetos e ao Desenvolvimento Iterativo