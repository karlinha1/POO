### Estrutura de Classes:

- **Definição:**
  - As classes em Java são modelos que descrevem o comportamento e os atributos de objetos.
  - Elas servem como moldes para criar objetos.

- **Atributos:**
  - Representam características ou propriedades dos objetos.
  - Podem ser variáveis que armazenam dados específicos para cada objeto.

- **Métodos:**
  - Definem o comportamento dos objetos, descrevendo as ações que podem ser realizadas por eles.
  - Contêm blocos de código que podem ser chamados para executar determinadas tarefas.

### Instanciação de Objetos:

- **Definição:**
  - Instanciar um objeto significa criar uma instância específica de uma classe.
  - Cada instância tem seu próprio conjunto de atributos, independentemente de outras instâncias.

- **Palavra-chave `new`:**
  - Utilizada para criar uma nova instância de uma classe.
  - Aloca memória para o objeto e chama o construtor da classe.

- **Construtor:**
  - É um método especial que é chamado automaticamente quando um objeto é criado.
  - É usado para inicializar os atributos do objeto e configurar seu estado inicial.

- **Exemplo de Instanciação:**
  ```java
  // Definição da classe
  public class Carro {
      // Atributos e métodos
  }

  // Instanciação do objeto
  Carro meuCarro = new Carro();

#EXEMPLO:
```java
    meuCarro.modelo = "Fusca";
    meuCarro.acelerar();
