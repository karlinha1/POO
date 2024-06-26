# Relações

## Herança:

A herança em Java permite que uma classe herde atributos e métodos de outra classe, chamada de classe pai ou superclasse.
Uma classe que herda é chamada de classe filha ou subclasse.
Para estabelecer uma relação de herança, utiliza-se a palavra-chave extends.

    public class Animal {
    // Atributos e métodos}

    
    public class Cachorro extends Animal {
    // Atributos e métodos específicos de Cachorro}
    
## Composição:

A composição é uma relação em que um objeto é composto por outros objetos.
É uma forma de construir classes complexas combinando outras classes menores.
Em Java, a composição é geralmente implementada através da criação de objetos dentro de uma classe.
    
    public class Carro {
    private Motor motor;

    
    private Roda[] rodas;
    // Outros atributos e métodos}


##Agregação:

A agregação é uma forma especial de composição em que um objeto é composto por outros objetos, mas esses objetos também podem existir independentemente do objeto principal.
Em Java, a agregação é semelhante à composição, mas os objetos podem ser compartilhados entre várias instâncias da classe principal.
    
    public class Time {
    private Jogador[] jogadores;
    // Outros atributos e métodos}


##Associação:

A associação é uma relação entre duas classes em que uma classe conhece a outra através de uma referência.
Pode ser bidirecional ou unidirecional.
Em Java, a associação é frequentemente implementada através de atributos que mantêm referências para outras classes.
    
    public class Pedido {
    private Cliente cliente;
    // Outros atributos e métodos}

##Dependência:

A dependência é uma relação em que uma classe usa outra classe temporariamente.
Não há propriedade entre as classes.
A dependência é geralmente expressa através de parâmetros de métodos ou variáveis locais.


    public class PedidoService {
    public void processarPedido(Pedido pedido) {
        // Lógica para processar o pedido}
}


#Main:
package relacoes;

        public class Relacoes { 
        public static void main(String[] args) {
        
        //Associação
        Carro carro = new Carro("Prata", new Pneu(255, 60, 18));   
        System.out.println(carro);
        
        //Composição        
        ContaCorrente contas[] = new ContaCorrente[2];
        contas[0] = new ContaCorrente("001", 1050, 15000);
        contas[1] = new ContaCorrente("002", 1060, 5000);
        
        ContaPoupanca poupanca[] = new ContaPoupanca[2];
        poupanca[0] = new ContaPoupanca("001", 1115, 150000);
        poupanca[1] = new ContaPoupanca("002", 1116, 500);
        
        Banco banco = new Banco("Banco do Brasil", contas, poupanca);
   
        System.out.println(banco);
        
        //Agregação
        Vendedor vendedor = new Vendedor(1,"Ruan");
        Comprador comprador = new Comprador(1, "Fulano");
        
        System.out.println(vendedor);
        System.out.println(comprador);
        
        Venda venda = new Venda(comprador, vendedor, "Sobonete");
        
        System.out.println(venda);
        
        venda = null;

        //venda é cancelada, mas o vendedor e comprador não deixam de existir
        System.out.println(venda);
        System.out.println(vendedor);
        System.out.println(comprador);
    } }

    #Classe1:
    
        package relacoes;

    public class Banco {
    //atributos
    String nome;
    ContaCorrente contasCorrente[];
    ContaPoupanca contasPoupanca[];

    public Banco(String nome, ContaCorrente[] contasCorrente, ContaPoupanca[] contasPoupanca) {
        this.nome = nome;
        this.contasCorrente = contasCorrente;
        this.contasPoupanca = contasPoupanca;
    }

    @Override
    public String toString() {
        String correnteStr = "", poupancaStr = "";
        for(int i = 0;i< contasCorrente.length;i++){
           correnteStr = correnteStr +" "+contasCorrente[i].toString();
        }
        
        for(int i = 0;i< contasPoupanca.length;i++){
            poupancaStr = poupancaStr +" "+contasPoupanca[i].toString();
        }
        
        return "Banco{" + "nome = " + nome + "\ncontasCorrente=" + correnteStr + "\ncontasPoupanca=" + poupancaStr + '}';
    } 
    }

    class Conta{
    String agencia;
    int numero;
    double saldo;

    public Conta(String agencia, int numero, double saldo) {
        this.agencia = agencia;
        this.numero = numero;
        this.saldo = saldo;
    }

    public String getAgencia() {
        return agencia;
    }

    public int getNumero() {
        return numero;
    }

    public double getSaldo() {
        return saldo;
    }

    public void setAgencia(String agencia) {
        this.agencia = agencia;
    }

    public void setNumero(int numero) {
        this.numero = numero;
    }

    public void setSaldo(double saldo) {
        this.saldo = saldo;
    }

    @Override
    public String toString() {
        return "\nConta{" + "agencia=" + agencia + ", numero=" + numero + ", saldo=" + saldo + '}';
    }
    
    }

    class ContaCorrente extends Conta{   
    ContaCorrente(String agencia, int numero, double saldo) {
        super(agencia, numero, saldo);
    }
    
    }

    class ContaPoupanca extends Conta{
       ContaPoupanca(String agencia, int numero, double saldo) {
        super(agencia, numero, saldo);}
        }

    #Classe2:
    package relacoes;

    public class Carro {
    //atributos
    String cor;
    Pneu p1, p2, p3, p4;
    
    //metodos
    public Carro(String cor, Pneu pneu) {
        this.cor = cor;
        this.p1 = pneu;
        this.p2 = pneu;
        this.p3 = pneu;
        this.p4 = pneu;
    }

    public String getCor() {
        return cor;
    }

    public Pneu getP1() {
        return p1;
    }

    public Pneu getP2() {
        return p2;
    }

    public Pneu getP3() {
        return p3;
    }

    public Pneu getP4() {
        return p4;
    }

    public void setCor(String cor) {
        this.cor = cor;
    }

    public void setP1(Pneu p1) {
        this.p1 = p1;
    }

    public void setP2(Pneu p2) {
        this.p2 = p2;
    }

    public void setP3(Pneu p3) {
        this.p3 = p3;
    }

    public void setP4(Pneu p4) {
        this.p4 = p4;
    }

    @Override
    public String toString() {
        return "Carro{" + "cor=" + cor + ", p1=" + p1 + ", p2=" + p2 + ", p3=" + p3 + ", p4=" + p4 + '}';
    }      
}

    class Pneu{
    //atributos
    private int largura;
    private int altura;
    private int aro;
    
    //metodos
    public Pneu(int largura, int altura, int aro) {
        this.largura = largura;
        this.altura = altura;
        this.aro = aro;
    }

    public int getLargura() {
        return largura;
    }

    public int getAltura() {
        return altura;
    }

    public int getAro() {
        return aro;
    }

    public void setLargura(int largura) {
        this.largura = largura;
    }

    public void setAltura(int altura) {
        this.altura = altura;
    }

    public void setAro(int aro) {
        this.aro = aro;
    }

    @Override
    public String toString() {
        return "Pneu{" + "largura=" + largura + ", altura=" + altura + ", aro=" + aro + '}';
    }   
    
}

    #Vendedor:
  
    
    package relacoes;


    public class Vendedor {
    //atributos
    private int codigo;
    private String nome;
    
    //metodos

    public Vendedor(int codigo, String nome) {
        this.codigo = codigo;
        this.nome = nome;
    }

    public int getCodigo() {
        return codigo;
    }

    public String getNome() {
        return nome;
    }

    public void setCodigo(int codigo) {
        this.codigo = codigo;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    @Override
    public String toString() {
        return "Vendedor{" + "codigo=" + codigo + ", nome=" + nome + '}';
    }
    
    }

    #Comprador:
   
    
    package relacoes;

    public class Comprador {
    //atributos
    private int codigo;
    private String nome;
    
    //metodos

    public Comprador(int codigo, String nome) {
        this.codigo = codigo;
        this.nome = nome;
    }

    public int getCodigo() {
        return codigo;
    }

    public String getNome() {
        return nome;
    }

    public void setCodigo(int codigo) {
        this.codigo = codigo;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    @Override
    public String toString() {
        return "Comprador{" + "codigo=" + codigo + ", nome=" + nome + '}';
    }
}
   

    
    #Venda:
   
    
    package relacoes;

    public class Venda {
    private Comprador comprador;
    private Vendedor vendedor;
    private String produto;

    public Venda(Comprador comprador, Vendedor vendedor, String produto) {
        this.comprador = comprador;
        this.vendedor = vendedor;
        this.produto = produto;
    }

    public Comprador getComprador() {
        return comprador;
    }

    public Vendedor getVendedor() {
        return vendedor;
    }

    public String getProduto() {
        return produto;
    }

    public void setComprador(Comprador comprador) {
        this.comprador = comprador;
    }

    public void setVendedor(Vendedor vendedor) {
        this.vendedor = vendedor;
    }

    public void setProduto(String produto) {
        this.produto = produto;
    }

    @Override
    public String toString() {
        return "Venda{" + comprador + "\n" + vendedor + "\nProduto=" + produto + '}';
    }
    }    


