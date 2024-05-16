### Herança

A herança é um conceito fundamental da programação orientada a objetos, permitindo a criação de hierarquias de classes onde uma classe (subclasse) pode herdar atributos e métodos de outra classe (superclasse). Em Java, isso é implementado usando a palavra-chave `extends`.

- **Superclasse (Classe Pai):**
  - É a classe da qual outras classes podem herdar atributos e métodos.
  - Pode ser chamada de classe base ou classe mãe.
  - Exemplo:
    ```java
    public class Animal {
        protected String nome;
        protected int idade;

        // Construtor e métodos
    }
    ```

- **Subclasse (Classe Filha):**
  - É a classe que herda da superclasse.
  - Pode adicionar novos atributos e métodos ou sobrescrever os existentes.
  - Exemplo:
    ```java
    public class Cachorro extends Animal {
        private String raca;

        // Construtor e métodos
    }
    ```

- **Palavra-chave `extends`:**
  - Usada para estabelecer uma relação de herança entre duas classes.
  - Indica que uma classe estende outra classe, ou seja, herda seus membros.
  - Exemplo:
    ```java
    public class Cachorro extends Animal {
        // Definição da subclasse
    }
    ```

- **Membros Herdados:**
  - As subclasses herdam todos os membros (atributos e métodos) da superclasse, exceto aqueles que são privados.
  - Os membros herdados podem ser acessados diretamente pela subclasse.
  - Exemplo:
    ```java
    public class Cachorro extends Animal {
        public void imprimirNome() {
            System.out.println(nome); // Acesso ao atributo herdado
        }
    }
    ```

- **Sobrescrita (Override):**
  - As subclasses podem fornecer uma implementação específica para um método herdado da superclasse.
  - O método na subclasse deve ter a mesma assinatura (nome e parâmetros) que o método na superclasse.
  - Exemplo:
    ```java
    @Override
    public void emitirSom() {
        System.out.println("O cachorro late.");
    }
    ```

A herança em Java é uma ferramenta poderosa para promover a reutilização de código e organizar classes em hierarquias relacionadas, o que leva a um design mais limpo e modular de programas orientados a objetos.


#MAIN:
    
    package poligono;

    public class Principal {

    public static void main(String[] args) {
          Triangulo t1 = new TrianguloEquilatero(10);
          Triangulo t2 = new TrianguloIsoceles(10,12);
          Triangulo t3 = new TrianguloEscaleno(9,10,11);
          
          System.out.println(t1);
          System.out.println(t2);
          System.out.println(t3);
         
    }   
    }

#Triangulo:

    package poligono;

    public class Triangulo {

    //atributos
    protected int base;
    protected int lado1, lado2;

    //Contrutor vazio
    public Triangulo() {

    }
    

    //Contrutor com parametros
    public Triangulo(int base, int lado1, int lado2) {
        this.base = base;
        this.lado1 = lado1;
        this.lado2 = lado2;
    }
    public int getBaseTriangulo() {    
        return base;
    }

    public int getLado1() {
        return lado1;
    }

    //Acessar os metodos
    //obter dados do objetos
    public int getLado2() {    
        return lado2;
    }

    //alterar dados do objetos

    public void setBase(int base) {
        this.base = base;
    }

    public void setLado1(int lado1) {
        this.lado1 = lado1;
    }

    public void setLado2(int lado2) {
        this.lado2 = lado2;
    }

    @Override
    public String toString() {
        return "Triangulo{" + "base: " + base + ", lado1: " + lado1 + ", lado2: " + lado2 + ", areaTriangulo: " + areaTriangulo();
    }

    //Comportamento do triangulo
    public double areaTriangulo() {
        if(this instanceof TrianguloEquilatero){
            //(lado^2 * raiz de 3)/4
            return (Math.pow(this.lado1, 2)* Math.sqrt(3))/4;
        }else if(this instanceof TrianguloEscaleno){
            double altura = (Math.sqrt(Math.pow(lado1, 2) - Math.pow(base/2, 2)));
            return base * altura/2;
        }else{
            double p = (base + lado1 + lado2)/2;
            return Math.sqrt(p*(p-base)*(p-lado1)*(p-lado2));
        }
    }
    }

  #Triangulo Equilátero:

     package poligono;

    public class TrianguloEquilatero extends Triangulo{

    public TrianguloEquilatero() {
    }

    public TrianguloEquilatero(int base) {
        super(base, base, base);
    }

    public int getLadoEquilatero() {
        return super.base;
    }

    public void setLadoEquilatero(int base) {
        super.base = base;
        super.lado1 = base;
        super.lado2 = base;
    }  
    
    @Override
    public String toString() {
        return super.toString() + ", Tipo - Equilatero}";
    }
    }

  #Triangulo Isoceles:

    
    package poligono;

    public class TrianguloIsoceles extends Triangulo{

    public TrianguloIsoceles() {
    }
    
    public TrianguloIsoceles(int base, int lado1) {
        super(base, lado1, lado1);
    }
    
    public int getBaseIsoceles() {
        return super.base;
    }
    
     public int getLadoIsoceles() {
        return super.lado1;
    }

    public void setBaseIsoceles(int base) {
        super.base = base;
    } 
    
    public void setLadoIsoceles(int lado) {
        super.lado1 = lado;
        super.lado2 = lado;
    }  
    
    @Override
    public String toString() {
        return super.toString() + ", Tipo - Isoceles}";
    }}
