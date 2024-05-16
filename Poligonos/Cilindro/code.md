### Composição:
- A composição é uma relação forte entre duas classes, em que uma classe é parte fundamental da outra.
- Na composição, um objeto é composto por outros objetos e não pode existir sem eles.
- A classe que contém os objetos é responsável por criar e gerenciar esses objetos.
- A composição é implementada fazendo com que a classe principal contenha objetos de outras classes como seus atributos.
- Exemplo:
  ```java
  public class Carro {
      private Motor motor;
      private Roda[] rodas;

      public Carro() {
          this.motor = new Motor();
          this.rodas = new Roda[4];
          // inicialização das rodas...
      }
  }
'''
### Agregação:
- A agregação é uma relação mais fraca entre duas classes, em que uma classe é composta por outras classes que podem existir independentemente.
- Na agregação, um objeto pode ser compartilhado entre várias instâncias da classe principal ou pode ser criado e destruído independentemente dela.
- A classe principal mantém uma referência para os objetos agregados, mas eles podem existir independentemente.
- Exemplo:
  
      public class Time {
      private List<Jogador> jogadores;

      public Time() {
          this.jogadores = new ArrayList<>();
      }

      public void adicionarJogador(Jogador jogador) {
          jogadores.add(jogador);
      }
  }

#Exemplo: Cilindro

    package poligono;

    public class Principal {

    public static void main(String[] args) {
            //Cilindro
            Cilindro c1 = new Cilindro(new Circunferencia(2), 5);
            
            System.out.println("Objeto Circulo: "+c1.getCirculo() + ", Altura: " + c1.getAltura());
            System.out.println(c1);
            Circunferencia circulo = new Circunferencia(5);
            
            c1.setCirculo(circulo);
            c1.setAltura(2);      
            
            System.out.println("Objeto Circulo: "+c1.getCirculo() + ", Altura: " + c1.getAltura());
            System.out.println(c1);                   
    }   
    }

  #Exemplo: Classe Cilindro
  
    package poligono;

    public class Cilindro {
    //atributos
    private Circunferencia circulo;
    private double altura;
     
    //Construtores
    public Cilindro(){
    }
    
    public Cilindro(Circunferencia circulo, double altura) {
        this.circulo = circulo;
        this.altura = altura;
    }
    
    public Circunferencia getCirculo() {
        return circulo;
    }

    public double getAltura() {
        return altura;
    }

    public void setCirculo(Circunferencia circulo) {
        this.circulo = circulo;
    }

    public void setAltura(double altura) {
        this.altura = altura;
    }
    
    public double areaCilindro(){
        return (2 * this.circulo.areaCircunferencia()) + 2 * Math.PI * this.circulo.getRaioCircunferencia() * altura;
    }

    @Override
    public String toString() {
        return "Cilindro{" + "Raio: " + circulo.getRaioCircunferencia() + ", Altura: " + altura + ", Area: "+areaCilindro() + '}';
    }
     }

  #Circunferencia:

  
    package poligono;

    public class Circunferencia {
    //atributos - característica
    public double raioCirc;
    
    //Construtor vazio, sem parametro
    public Circunferencia() {
        
    }
    
    //Construtor com parâmetro
    public Circunferencia(double raioCirc) {
        this.raioCirc = raioCirc;
    }
    
    //Acessar os metodos
    //obter dados do objetos
    public double getRaioCirc() {
        return raioCirc;
    }

    //alterar dados do objetos
    public void setRaioCirc(double raioCirc) {
        this.raioCirc = raioCirc;
    }

    //retorna uma string que "textualmente representa" esse objeto
    @Override
    public String toString() {
        return "Circunferencia {" + "raioCirc = " + raioCirc + '}';
    }
    
    //métodos - comportamento do objeto
    public double areaCirc(){
        return  (Math.pow(raioCirc, 2) * Math.PI);
    }
    }
