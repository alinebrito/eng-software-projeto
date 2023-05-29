
Versão inicial:

```java
enum TipoCasa {
		COMUM, PARTIDA, IMPOSTO_RENDA
}

class Casa{

  void atingida(TipoCasa tipoCasa){
    switch (tipoCasa) {
       case COMUM:
          System.out.println("Casa Comum atingida.");
          break;
       case PARTIDA:
         System.out.println("Casa de Partida atingida.");
          break;
       case IMPOSTO_RENDA:
          System.out.println("Casa de Imposto de Renda atingida.");
          break;
       default:
          throw new IllegalArgumentException("Casa Incorreta");
    }
  }
  
}


public class Main {
  public static void main(String[] args) {
    Casa casa  = new Casa();
    casa.atingida(TipoCasa.COMUM);
  }
}
```

Versão após mudanças:

```java

abstract class Casa{

  abstract void atingida();
}

class CasaPartida extends Casa{
    void atingida(){
      System.out.println("Casa de Partida atingida.");
      return;
    }
}

class CasaComum extends Casa{
    void atingida(){
      System.out.println("Casa Comum atingida.");
      return;
    }
}

class CasaImpostoRenda extends Casa{
    void atingida(){
      System.out.println("Casa de Imposto de Renda atingida.");
      return;
    }
}

public class Main {
  public static void main(String[] args) {
    Casa casa = new CasaPartida();
    casa.atingida();
  }
}


```