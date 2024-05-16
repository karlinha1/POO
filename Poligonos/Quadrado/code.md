#:MAIN
    
    package poligono;

    public class Principal {

    public static void main(String[] args) {
          //Quadrado
          Quadrado q1 = new Quadrado(5);
          
          System.out.println(q1);
          
          q1.setLado(6);
          
          System.out.println("Lado do triangulo: " + q1.getLado());
    }
    }

#Classe Quadrado:
    
    package poligono;
    //Quadrado é uma especifidade de Retangulo
    //Reusabilidade da classe Retangulo
    public class Quadrado extends Retangulo {

    Quadrado() {
    }

    //Construtor herdando os paramentros da Classe Mãe
    Quadrado(int lado) {
        super(lado, lado);
    }

    //set herdando o set da Classe Mãe
    public void setLado(int lado) {
        super.setAlturaRetangulo(lado);
        super.setBaseRetangulo(lado);
    }

    //get herdando o get da Classe Mãe
    public int getLado() {
        return super.getAlturaRetangulo();
    }

    @Override
    public String toString() {
        return super.toString() + " Tipo: Quadrado";
    }  
}
```
