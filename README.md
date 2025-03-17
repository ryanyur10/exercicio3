# Exercicio3

Veiculo.java

abstract class Veiculo {
    protected String marca;

    public Veiculo(String marca) {
        this.marca = marca;
    }

    public abstract void exibirDetalhes();
}

Carro.java

class Carro extends Veiculo {
    private int portas;

    public Carro(String marca) {
        super(marca);
    }

    // Sobrecarga para definir portas com tipo int
    public void definirDetalhes(int portas) {
        this.portas = portas;
    }

    // Sobrecarga para definir portas com tipo String
    public void definirDetalhes(String portas) {
        this.portas = Integer.parseInt(portas);
    }

    @Override
    public void exibirDetalhes() {
        System.out.println("Marca: " + marca + ", Portas: " + portas);
    }
}

Moto.java

class Moto extends Veiculo {
    private int cilindradas;

    public Moto(String marca) {
        super(marca);
    }

    public void definirDetalhes(int cilindradas) {
        this.cilindradas = cilindradas;
    }

    @Override
    public void exibirDetalhes() {
        System.out.println("Marca: " + marca + ", Cilindradas: " + cilindradas);
    }
}

Main.java

public class Main {
    public static void main(String[] args) {
        Carro carro = new Carro("Fiat");
        carro.definirDetalhes(4);
        carro.exibirDetalhes();

        Moto moto = new Moto("Yamaha");
        moto.definirDetalhes(250);
        moto.exibirDetalhes();
    }
}


Exercício 2: Sistema de Funcionários
Funcionario.java

abstract class Funcionario {
    protected String nome;

    public Funcionario(String nome) {
        this.nome = nome;
    }

    public abstract double calcularSalario();
}

Gerente.java

class Gerente extends Funcionario {
    private double bonus;

    public Gerente(String nome) {
        super(nome);
    }

    // Sobrecarga para definir bônus com tipo double
    public void definirBonus(double bonus) {
        this.bonus = bonus;
    }

    // Sobrecarga para definir bônus com tipo int
    public void definirBonus(int bonus) {
        this.bonus = (double) bonus;
    }

    @Override
    public double calcularSalario() {
        return 5000 + bonus;
    }
}

Desenvolvedor.java

class Desenvolvedor extends Funcionario {
    private int horasTrabalhadas;

    public Desenvolvedor(String nome) {
        super(nome);
    }

    public void definirHorasTrabalhadas(int horas) {
        this.horasTrabalhadas = horas;
    }

    @Override
    public double calcularSalario() {
        return horasTrabalhadas * 50;
    }
}

Main.java

public class Main {
    public static void main(String[] args) {
        Gerente gerente = new Gerente("Carlos");
        gerente.definirBonus(1000);
        System.out.println("Salário do Gerente: " + gerente.calcularSalario());

        Desenvolvedor dev = new Desenvolvedor("Ana");
        dev.definirHorasTrabalhadas(160);
        System.out.println("Salário do Desenvolvedor: " + dev.calcularSalario());
    }
}


Exercício 3: Animais Marinhos
AnimalMarinho.java

abstract class AnimalMarinho {
    protected String habitat;

    public AnimalMarinho(String habitat) {
        this.habitat = habitat;
    }

    public abstract void fazerSom();
}

Golfinho.java

class Golfinho extends AnimalMarinho {
    private int saltos;

    public Golfinho(String habitat) {
        super(habitat);
    }

    // Sobrecarga para definir saltos com tipo int
    public void definirSaltos(int saltos) {
        this.saltos = saltos;
    }

    // Sobrecarga para definir saltos com tipo double
    public void definirSaltos(double saltos) {
        this.saltos = (int) saltos;
    }

    @Override
    public void fazerSom() {
        System.out.println("Som do Golfinho: 'Eiii!'");
    }
}

Tubarao.java

class Tubarao extends AnimalMarinho {
    private int dentes;

    public Tubarao(String habitat) {
        super(habitat);
    }

    public void definirDentes(int dentes) {
        this.dentes = dentes;
    }

    @Override
    public void fazerSom() {
        System.out.println("Som do Tubarão: 'Grunhido'");
    }
}

Main.java
public class Main {
    public static void main(String[] args) {
        Golfinho golfinho = new Golfinho("Oceano");
        golfinho.definirSaltos(5);
        golfinho.fazerSom();

        Tubarao tubarao = new Tubarao("Mar aberto");
        tubarao.definirDentes(50);
        tubarao.fazerSom();
    }
}


Exercício 4: Sistema de Contas Bancárias
Conta.java

abstract class Conta {
    protected double saldo;

    public Conta(double saldo) {
        this.saldo = saldo;
    }

    public abstract void calcularJuros();
}

ContaPoupanca.java

class ContaPoupanca extends Conta {
    private double taxaRendimento;

    public ContaPoupanca(double saldo) {
        super(saldo);
    }

    // Sobrecarga para definir taxa de rendimento com tipo double
    public void definirTaxa(double taxa) {
        this.taxaRendimento = taxa;
    }

    // Sobrecarga para definir taxa de rendimento com tipo int
    public void definirTaxa(int taxa) {
        this.taxaRendimento = (double) taxa;
    }

    @Override
    public void calcularJuros() {
        double juros = saldo * (taxaRendimento / 100);
        System.out.println("Juros: " + juros);
    }
}

ContaCorrente.java

class ContaCorrente extends Conta {
    private double limite;

    public ContaCorrente(double saldo) {
        super(saldo);
    }

    public void definirLimite(double limite) {
        this.limite = limite;
    }

    @Override
    public void calcularJuros() {
        double juros = saldo * 0.05;
        System.out.println("Juros Conta Corrente: " + juros);
    }
}

Main.java

public class Main {
    public static void main(String[] args) {
        ContaPoupanca poupanca = new ContaPoupanca(1000);
        poupanca.definirTaxa(5);
        poupanca.calcularJuros();

        ContaCorrente corrente = new ContaCorrente(2000);
        corrente.definirLimite(500);
        corrente.calcularJuros();
    }
}


Exercício 5: Loja de Eletrônicos
Eletronico.java

abstract class Eletronico {
    protected String marca;

    public Eletronico(String marca) {
        this.marca = marca;
    }

    public abstract void ligar();
}

Celular.java

class Celular extends Eletronico {
    private double tela;

    public Celular(String marca) {
        super(marca);
    }

    // Sobrecarga para definir tamanho da tela com tipo double
    public void definirTela(double tela) {
        this.tela = tela;
    }

    // Sobrecarga para definir tamanho da tela com tipo int
    public void definirTela(int tela) {
        this.tela = (double) tela;
    }

    @Override
    public void ligar() {
        System.out.println("Celular " + marca + " ligado!");
    }
}

Notebook.java


class Notebook extends Eletronico {
    private int ram;

    public Notebook(String marca) {
        super(marca);
    }

    public void definirRam(int ram) {
        this.ram = ram;
    }

    @Override
    public void ligar() {
        System.out.println("Notebook " + marca + " ligado!");
    }
}

Main.java

public class Main {
    public static void main(String[] args) {
        Celular celular = new Celular("Samsung");
        celular.definirTela(6.5);
        celular.ligar();

        Notebook notebook = new Notebook("Dell");
        notebook.definirRam(16);
        notebook.ligar();
    }
}


Exercício 6: Tipos de Pagamento
Pagamento.java

abstract class Pagamento {
    protected double valor;

    public Pagamento(double valor) {
        this.valor = valor;
    }

    public abstract void processarPagamento();
}

CartaoCredito.java
java

class CartaoCredito extends Pagamento {
    private double limite;

    public CartaoCredito(double valor) {
        super(valor);
    }

    // Sobrecarga para definir limite com tipo double
    public void definirLimite(double limite) {
        this.limite = limite;
    }

    // Sobrecarga para definir limite com tipo int
    public void definirLimite(int limite) {
        this.limite = (double) limite;
    }

    @Override
    public void processarPagamento() {
        System.out.println("Pagamento de " + valor + " realizado com Cartão de Crédito.");
    }
}

Boleto.java
java

class Boleto extends Pagamento {
    private String codigoBarras;

    public Boleto(double valor) {
        super(valor);
    }

    public void definirCodigo(String codigo) {
        this.codigoBarras = codigo;
    }

    @Override
    public void processarPagamento() {
        System.out.println("Pagamento de " + valor + " realizado com Boleto.");
    }
}

Main.java
java

public class Main {
    public static void main(String[] args) {
        CartaoCredito cartao = new CartaoCredito(150.00);
        cartao.definirLimite(5000);
        cartao.processarPagamento();

        Boleto boleto = new Boleto(200.00);
        boleto.definirCodigo("123456789");
        boleto.processarPagamento();
    }
}


Exercício 7: Personagens de Jogo
Personagem.java
java
Copiar
abstract class Personagem {
    protected int energia;

    public Personagem(int energia) {
        this.energia = energia;
    }

    public abstract void atacar();
}

Mago.java
java
Copiar
class Mago extends Personagem {
    private double mana;

    public Mago(int energia) {
        super(energia);
    }

    // Sobrecarga para definir mana com tipo double
    public void definirMana(double mana) {
        this.mana = mana;
    }

    // Sobrecarga para definir mana com tipo int
    public void definirMana(int mana) {
        this.mana = (double) mana;
    }

    @Override
    public void atacar() {
        System.out.println("Mago ataca com " + mana + " de mana!");
    }
}

Guerreiro.java
java
Copiar
class Guerreiro extends Personagem {
    private int forca;

    public Guerreiro(int energia) {
        super(energia);
    }

    public void definirForca(int forca) {
        this.forca = forca;
    }

    @Override
    public void atacar() {
        System.out.println("Guerreiro ataca com " + forca + " de força!");
    }
}

Main.java

public class Main {
    public static void main(String[] args) {
        Mago mago = new Mago(100);
        mago.definirMana(50);
        mago.atacar();

        Guerreiro guerreiro = new Guerreiro(200);
        guerreiro.definirForca(80);
        guerreiro.atacar();
    }
}


Exercício 8: Tipos de Transporte
Transporte.java

abstract class Transporte {
    protected int capacidade;

    public Transporte(int capacidade) {
        this.capacidade = capacidade;
    }

    public abstract void mover();
}

Navio.java

class Navio extends Transporte {
    private double tonelagem;

    public Navio(int capacidade) {
        super(capacidade);
    }

    // Sobrecarga para definir tonelagem com tipo double
    public void definirTonelagem(double tonelagem) {
        this.tonelagem = tonelagem;
    }

    // Sobrecarga para definir tonelagem com tipo int
    public void definirTonelagem(int tonelagem) {
        this.tonelagem = (double) tonelagem;
    }

    @Override
    public void mover() {
        System.out.println("Navio movendo com capacidade de " + capacidade + " passageiros.");
    }
}

Avião.java
class Aviao extends Transporte {
    private int altitudeMaxima;

    public Aviao(int capacidade) {
        super(capacidade);
    }

    public void definirAltitude(int altitude) {
        this.altitudeMaxima = altitude;
    }

    @Override
    public void mover() {
        System.out.println("Avião movendo a " + altitudeMaxima + " metros de altitude.");
    }
}

Main.java
java
Copiar
public class Main {
    public static void main(String[] args) {
        Navio navio = new Navio(100);
        navio.definirTonelagem(20000);
        navio.mover();

        Aviao aviao = new Aviao(200);
        aviao.definirAltitude(10000);
        aviao.mover();
    }
}


2°


Lista de Exercícios - Getters, Setters, Polimorfismo e Herança 3°
1:class Escola:
    def init(self, nome, endereco):
        self.__nome = nome  
        self.__endereco = endereco  

    # Getter para o atributo nome
    def get_nome(self):
        return self.__nome

    # Setter para o atributo nome
    def set_nome(self, nome):
        self.__nome = nome

    # Getter para o atributo endereco
    def get_endereco(self):
        return self.__endereco

    # Setter para o atributo endereco
    def set_endereco(self, endereco):
        self.__endereco = endereco
Testando a classe Escola:

escola1 = Escola("Escola ABC", "Rua das Flores, 123")

print("Nome da escola:", escola1.get_nome())
print("Endereço da escola:", escola1.get_endereco())

escola1.set_nome("Escola XYZ")
escola1.set_endereco("Avenida Central, 456")

print("Novo nome da escola:", escola1.get_nome())
print("Novo endereço da escola:", escola1.get_endereco())

2:class Escola:
    def _init_(self, nome, endereco):
        self.__nome = nome  
        self.__endereco = endereco  

    def get_nome(self):
        return self.__nome

    def set_nome(self, nome):
        self.__nome = nome

    def get_endereco(self):
        return self.__endereco

    def set_endereco(self, endereco):
        self.__endereco = endereco
class Curso(Escola):
    def _init_(self, nome, endereco, cargaHoraria):
        # Chamando o construtor da classe base (Escola)
        super()._init_(nome, endereco)
        self.__cargaHoraria = cargaHoraria  
 
    def get_cargaHoraria(self):
        return self.__cargaHoraria

    def set_cargaHoraria(self, cargaHoraria):
        self.__cargaHoraria = cargaHoraria
        # Criando uma instância da classe Curso
curso1 = Curso("Curso de Python", "Avenida dos Programadores, 101", 120)


print("Nome da escola:", curso1.get_nome())
print("Endereço da escola:", curso1.get_endereco())
print("Carga horária do curso:", curso1.get_cargaHoraria())

curso1.set_nome("Curso de Java")
curso1.set_endereco("Rua da Tecnologia, 200")
curso1.set_cargaHoraria(150)

print("Novo nome do curso:", curso1.get_nome())
print("Novo endereço do curso:", curso1.get_endereco())
print("Nova carga horária do curso:", curso1.get_cargaHoraria())

3:class Escola:
    def _init_(self, nome, endereco):
        self.__nome = nome  
        self.__endereco = endereco  

    def get_nome(self):
        return self.__nome
 
    def set_nome(self, nome):
        self.__nome = nome

    def get_endereco(self):
        return self.__endereco

    def set_endereco(self, endereco):
        self.__endereco = endereco

class Curso(Escola):
    def _init_(self, nome, endereco, cargaHoraria):
        # Chamando o construtor da classe base (Escola)
        super()._init_(nome, endereco)
        self.__cargaHoraria = cargaHoraria
    
    def get_cargaHoraria(self):
        return self.__cargaHoraria

    def set_cargaHoraria(self, cargaHoraria):
        self.__cargaHoraria = cargaHoraria

    def exibirInformacoes(self):
        print(f"Nome: {self.get_nome()}")
        print(f"Endereço: {self.get_endereco()}")
        print(f"Carga Horária: {self.get_cargaHoraria()} horas")
class CursoTecnico(Curso):
    def _init_(self, nome, endereco, cargaHoraria, modalidade):
     
        super()._init_(nome, endereco, cargaHoraria)
        self.__modalidade = modalidade  # Atributo privado específico de CursoTecnico

    def get_modalidade(self):
        return self.__modalidade
 
    def set_modalidade(self, modalidade):
        self.__modalidade = modalidade

    def exibirInformacoes(self):
        super().exibirInformacoes()  
        print(f"Modalidade: {self.get_modalidade()}")

curso1 = Curso("Curso de Python", "Avenida dos Programadores, 101", 120)

print("Informações do Curso:")
curso1.exibirInformacoes()


curso_tecnico = CursoTecnico("Curso Técnico em Redes", "Rua da Tecnologia, 200", 200, "Presencial")

print("\nInformações do Curso Técnico:")
curso_tecnico.exibirInformacoes()

4:class Escola:
    def _init_(self, nome, endereco):
        self.__nome = nome  
        self.__endereco = endereco  
  
    def get_nome(self):
        return self.__nome

    def set_nome(self, nome):
        self.__nome = nome

    def get_endereco(self):
        return self.__endereco
  
    def set_endereco(self, endereco):
        self.__endereco = endereco
class Curso(Escola):
    def _init_(self, nome, endereco, cargaHoraria):
     
        super()._init_(nome, endereco)
        self.__cargaHoraria = cargaHoraria  
   
    def get_cargaHoraria(self):
        return self.__cargaHoraria

    def set_cargaHoraria(self, cargaHoraria):
        self.__cargaHoraria = cargaHoraria

    def exibirInformacoes(self):
        print(f"Nome: {self.get_nome()}")
        print(f"Endereço: {self.get_endereco()}")
        print
class CursoTecnico(Curso):
    def _init_(self, nome, endereco, cargaHoraria, modalidade):
     
        super()._init_(nome, endereco, cargaHoraria)
        self.__modalidade = modalidade 
  
    def get_modalidade(self):
        return self.__modalidade
   
    def set_modalidade(self, modalidade):
        self.__modalidade = modalidade

    def exibirInformacoes(self):
        super().exibirInformacoes()  # Chama o método da classe base (Curso)
        print(f"Modalidade: {self.get_modalidade()}")

curso1 = Curso("Curso de Python", "Avenida dos Programadores, 101", 120)

print("Informações do Curso:")
curso1.exibirInformacoes()

curso_tecnico = CursoTecnico("Curso Técnico em Redes", "Rua da Tecnologia, 200", 200, "Presencial")

print("\nInformações do Curso Técnico:")
curso_tecnico.exibirInformacoes()

5:class Escola:
    def _init_(self, nome, endereco):
        self.__nome = nome  # Atributo privado
        self.__endereco = endereco  # Atributo privado
 
    def get_nome(self):
        return self.__nome

    def set_nome(self, nome):
        self.__nome = nome

    def get_endereco(self):
        return self.__endereco

    def set_endereco(self, endereco):
        self.__endereco = endereco
class Curso(Escola):
    def _init_(self, nome, endereco, cargaHoraria):
        # Chamando o construtor da classe base (Escola) para inicializar nome e endereco
        super()._init_(nome, endereco)
        self.__cargaHoraria = cargaHoraria  # Atributo privado específico de Curso
  
    def get_cargaHoraria(self):
        return self.__cargaHoraria

    def set_cargaHoraria(self, cargaHoraria):
        self.__cargaHoraria = cargaHoraria

    def exibirInformacoes(self):
        print(f"Nome: {self.get_nome()}")
        print(f"Endereço: {self.get_endereco()}")
        print(f"Carga Horária: {self.get_cargaHoraria()} horas")
class CursoTecnico(Curso):
    def _init_(self, nome, endereco, cargaHoraria, modalidade):
        # Chamando o construtor da classe base (Curso) para inicializar nome, endereco e cargaHoraria
        super()._init_(nome, endereco, cargaHoraria)
        self.__modalidade = modalidade  # Atributo privado específico de CursoTecnico
        
    def get_modalidade(self):
        return self.__modalidade

    def set_modalidade(self, modalidade):
        self.__modalidade = modalidade

    def exibirInformacoes(self):
        super().exibirInformacoes() 
        print(f"Modalidade: {self.get_modalidade()}")
class Main:
    @staticmethod
    def main():
       
        curso1 = Curso("Curso de Python", "Avenida dos Programadores, 101", 120)

        print("Informações do Curso:")
        curso1.exibirInformacoes()
      
        curso_tecnico = CursoTecnico("Curso Técnico em Redes", "Rua da Tecnologia, 200", 200, "Presencial")

        print("\nInformações do Curso Técnico:")
        curso_tecnico.exibirInformacoes()

if _name_ == "_main_":
    Main.main()

6:class Escola:
    def _init_(self, nome, endereco):
        self.__nome = nome  # Atributo privado
        self.__endereco = endereco  # Atributo privado

    def get_nome(self):
        return self.__nome

    def set_nome(self, nome):
        self.__nome = nome

    def get_endereco(self):
        return self.__endereco
    
    def set_endereco(self, endereco):
        self.__endereco = endereco
class Curso(Escola):
    def _init_(self, nome, endereco, cargaHoraria):
        # Chamando o construtor da classe base (Escola) para inicializar nome e endereco
        super()._init_(nome, endereco)
        self.__cargaHoraria = cargaHoraria  # Atributo privado específico de Curso

    def get_cargaHoraria(self):
        return self.__cargaHoraria

    def set_cargaHoraria(self, cargaHoraria):
        if cargaHoraria > 0:
            self.__cargaHoraria = cargaHoraria
        else:
            print("Erro: A carga horária deve ser maior que zero!")

    def exibirInformacoes(self):
        print(f"Nome: {self.get_nome()}")
        print(f"Endereço: {self.get_endereco()}")
        print(f"Carga Horária: {self.get_cargaHoraria()} horas")
class CursoTecnico(Curso):
    def _init_(self, nome, endereco, cargaHoraria, modalidade):
        # Chamando o construtor da classe base (Curso) para inicializar nome, endereco e cargaHoraria
        super()._init_(nome, endereco, cargaHoraria)
        self.__modalidade = modalidade  # Atributo privado específico de CursoTecnico

    def get_modalidade(self):
        return self.__modalidade

    def set_modalidade(self, modalidade):
        self.__modalidade = modalidade

    def exibirInformacoes(self):
        super().exibirInformacoes()  # Chama o método da classe base (Curso)
        print(f"Modalidade: {self.get_modalidade()}")
class Main:
    @staticmethod
    def main():
        
        curso1 = Curso("Curso de Python", "Avenida dos Programadores, 101", 120)
   
        print("Informações do Curso:")
        curso1.exibirInformacoes()
    
        print("\nTentando definir carga horária negativa:")
        curso1.set_cargaHoraria(-50)  # Deveria mostrar um erro

       print("\nDefinindo carga horária positiva:")
        curso1.set_cargaHoraria(150)
        curso1.exibirInformacoes()  # Exibindo informações novamente após alteração

        curso_tecnico = CursoTecnico("Curso Técnico em Redes", "Rua da Tecnologia, 200", 200, "Presencial")

        print("\nInformações do Curso Técnico:")
        curso_tecnico.exibirInformacoes()
        
if _name_ == "_main_":
    Main.main()

7:class Escola:
    def _init_(self, nome, endereco):
        self.__nome = nome  # Atributo privado
        self.__endereco = endereco  # Atributo privado

    def get_nome(self):
        return self.__nome

    def set_nome(self, nome):
        self.__nome = nome

    def get_endereco(self):
        return self.__endereco

    def set_endereco(self, endereco):
        self.__endereco = endereco
class Curso(Escola):
    def _init_(self, nome, endereco, cargaHoraria):
        super()._init_(nome, endereco)
        self.__cargaHoraria = cargaHoraria  # Atributo privado específico de Curso
        
    def get_cargaHoraria(self):
        return self.__cargaHoraria

    def set_cargaHoraria(self, cargaHoraria):
        if cargaHoraria > 0:
            self.__cargaHoraria = cargaHoraria
        else:
            print("Erro: A carga horária deve ser maior que zero!")
 
    def exibirInformacoes(self):
        print(f"Nome: {self.get_nome()}")
        print(f"Endereço: {self.get_endereco()}")
        print(f"Carga Horária: {self.get_cargaHoraria()} horas")
class CursoTecnico(Curso):
    def _init_(self, nome, endereco, cargaHoraria, modalidade):
     
        super()._init_(nome, endereco, cargaHoraria)
        self.__modalidade = modalidade  # Atributo privado específico de CursoTecnico

    def get_modalidade(self):
        return self.__modalidade
  
    def set_modalidade(self, modalidade):
        self.__modalidade = modalidade

    def exibirInformacoes(self):
     
        super().exibirInformacoes()  # Isso chama o método da classe Curso
        print(f"Modalidade: {self.get_modalidade()}")
   class Main:
    @staticmethod
    def main():
       
        curso1 = Curso("Curso de Python", "Avenida dos Programadores, 101", 120)

        print("Informações do Curso:")
        curso1.exibirInformacoes()
       
        curso_tecnico = CursoTecnico("Curso Técnico em Redes", "Rua da Tecnologia, 200", 200, "Presencial")

        print("\nInformações do Curso Técnico:")
        curso_tecnico.exibirInformacoes()
if _name_ == "_main_":
    Main.main()
    
8:from abc import ABC, abstractmethod

class Escola(ABC):
    def _init_(self, nome, endereco):
        self.__nome = nome  # Atributo privado
        self.__endereco = endereco  # Atributo privado

    def get_nome(self):
        return self.__nome

    def set_nome(self, nome):
        self.__nome = nome

    def get_endereco(self):
        return self.__endereco

    def set_endereco(self, endereco):
        self.__endereco = endereco

    @abstractmethod
    def calcularMensalidade(self):
        pass
class Curso(Escola):
    def _init_(self, nome, endereco, cargaHoraria):
        super()._init_(nome, endereco)
        self.__cargaHoraria = cargaHoraria  
        
    def get_cargaHoraria(self):
        return self.__cargaHoraria

    def set_cargaHoraria(self, cargaHoraria):
        if cargaHoraria > 0:
            self.__cargaHoraria = cargaHoraria
        else:
            print("Erro: A carga horária deve ser maior que zero!")
   
    def calcularMensalidade(self):
        return 500
class CursoTecnico(Curso):
    def _init_(self, nome, endereco, cargaHoraria, modalidade):
        super()._init_(nome, endereco, cargaHoraria)
        self.__modalidade = modalidade  

    def get_modalidade(self):
        return self.__modalidade

    def set_modalidade(self, modalidade):
        self.__modalidade = modalidade

    def calcularMensalidade(self):
        mensalidade_base = super().calcularMensalidade()  
        acréscimo = (self.get_cargaHoraria() // 10) * 50
        return mensalidade_base + acréscimo
