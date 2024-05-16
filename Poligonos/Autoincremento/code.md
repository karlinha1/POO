# Modificadores de Acesso:

Os modificadores de acesso em Java controlam a visibilidade de classes, métodos e atributos. Existem quatro tipos principais de modificadores de acesso: public, private, protected e o padrão (sem especificação).

- **public**: Acesso irrestrito a todos os outros pacotes.
- **private**: Acesso restrito apenas à própria classe.
- **protected**: Acesso permitido à própria classe e às suas subclasses.
- **Padrão**: Acesso permitido apenas dentro do mesmo pacote.

# Métodos e Atributos Estáticos:

Métodos e atributos estáticos pertencem à classe em vez de instâncias individuais da classe. Eles são compartilhados por todas as instâncias da classe. Métodos estáticos são invocados usando o nome da classe, sem a necessidade de criar um objeto da classe. Atributos estáticos são declarados com a palavra-chave `static` e podem ser acessados diretamente ou através do nome da classe. São úteis para definir variáveis ​​ou métodos que devem ser compartilhados por todas as instâncias da classe.

    public class Exemplo {
    private static int contador = 0; // Atributo estático

    public static void incrementarContador() { // Método estático
        contador++;
    }

    public static int getContador() { // Método estático
        return contador;
    }
    }

    Exemplo.incrementarContador();
    int valor = Exemplo.getContador();


#Exercicio de autoincremento:
##Classe: Cliente


    package clientes;

    import java.util.ArrayList;
    import java.util.List;
    import javax.swing.JOptionPane;

    public class Clientes {
    
    //atributo estatico
    static List<Cadastro>clientes = new ArrayList<Cadastro>();
    
    //metodo estatico
    static void inserirCliente(String nome){
        Cadastro c = new Cadastro(nome);
        clientes.add(c);
    }
    
    public static void main(String[] args) {
        //Aparecer janela para digitar nome
        for(int i = 0; i < 5; i++){
            inserirCliente(JOptionPane.showInputDialog("Nome:"));
        }
        //Aparecer janela nomes digitados
        for(Cadastro cliente: clientes){
            JOptionPane.showMessageDialog(null, cliente);
        }
        
        System.out.println(clientes);
       
      //metodo anteriormente aprendido para instanciar um objeto
    //    Cadastro c1 = new Cadastro("Bruna");
    //    Cadastro c2 = new Cadastro("Marcos");
    //    Cadastro c3 = new Cadastro("Wagner");
    //
    //    System.out.println(c1);
    //    System.out.println(c2);
    //    System.out.println(c3);
        
        
      }}

  
  ##Classe: Cadastro
  
    package clientes;

    public class Cadastro {
    
    //atributos
    private int codCliente;
    private String nomeCliente;
    
    //metodo estatico 
    static int codClienteStatic = 0;

    public Cadastro(String nomeCliente) {
        this.codCliente = ++codClienteStatic;
        this.nomeCliente = nomeCliente;
    }

    public int getCodCliente() {
        return codCliente;
    }

    public String getNomeCliente() {
        return nomeCliente;
    }

    public void setCodCliente(int codCliente) {
        this.codCliente = codCliente;
    }

    public void setNomeCliente(String nomeCliente) {
        this.nomeCliente = nomeCliente;
    }

    @Override
    public String toString() {
        return "Cadastro{" + "Codigo: " + codCliente + ", Nome: " + nomeCliente + '}';
    }
    }
