# HERANÇA 2

Segundo exercício sobre Herança

## 🚀 Começando

Uma empresa necessita de um sistema informatizado. Nesse sistema serão cadastrados todos os vendedores, gerentes e clientes.

Os dados de um vendedor são: nome, cpf, data de nascimento, data de contratação, salário base, e percentual de comissão.

Os dados de um gerente são:  nome, cpf, data de nascimento, data de contratação, salário base, e departamento.

Os dados de um cliente são:  nome, cpf, data de nascimento, email, número cartão de fidelidade e telefone.

Crie classes adequadas a esses dados.

Todas as classes devem ter seus atributos encapsulados e métodos construtores. 

### 📋 Pré-requisitos

import java.time.LocalDate;

class Pessoa { // Criando a classe base na qual os outros irão herdar
    private String nome;
    private String cpf;
    private LocalDate dataNascimento;

    public Pessoa(String nome, String cpf, LocalDate dataNascimento) {
        this.nome = nome;
        this.cpf = cpf;
        this.dataNascimento = dataNascimento;
    }

    public String getNome() { // Método Getters para acessar os atributos privados
        return nome;
    }

    public String getCpf() {
        return cpf;
    }

    public LocalDate getDataNascimento() {
        return dataNascimento;
    }

    String descricao() { // Criação do retorno que dará o visual ao gerar o código
        return 
            "Nome: " + this.nome + "\n" + 
            "CPF: " + this.cpf + "\n" + 
            "Data de Nascimento: " + this.dataNascimento + "\n";
    }
}

class Vendedor extends Pessoa { // Classe de vendedor que herda os atributos de classe pessoa, acrescentando data de contratação, salário base e percentual de comissão
    private LocalDate dataContratacao;
    private double salarioBase;
    private double percentualComissao;

    public Vendedor(String nome, String cpf, LocalDate dataNascimento, LocalDate dataContratacao, double salarioBase, double percentualComissao) {
        super(nome, cpf, dataNascimento); // Utiliza o construtor super pois herda da superclasse Pessoa
        this.dataContratacao = dataContratacao;
        this.salarioBase = salarioBase;
        this.percentualComissao = percentualComissao;
    }

    public LocalDate getDataContratacao() {
        return dataContratacao;
    }

    public double getSalarioBase() {
        return salarioBase;
    }

    public double getPercentualComissao() {
        return percentualComissao;
    }

    String descricao() { // Criação do retorno que dará o visual ao gerar o código
        return super.descricao() +
               "Data de Contratação: " + this.dataContratacao + "\n" + 
               "Salário Base: R$ " + this.salarioBase + "\n" +
               "Percentual de Comissão: " + this.percentualComissao + "%\n";
    }
}

class Gerente extends Pessoa { // Classe de gerente que herda os atributos de classe pessoa, acrescentando data de contratação, salário base e o departamento
    private LocalDate dataContratacao;
    private double salarioBase;
    private String departamento;

    public Gerente(String nome, String cpf, LocalDate dataNascimento, LocalDate dataContratacao, double salarioBase, String departamento) {
        super(nome, cpf, dataNascimento); // Utiliza o construtor super pois herda da superclasse Pessoa
        this.dataContratacao = dataContratacao;
        this.salarioBase = salarioBase;
        this.departamento = departamento;
    }

    public LocalDate getDataContratacao() {
        return dataContratacao;
    }

    public double getSalarioBase() {
        return salarioBase;
    }

    public String getDepartamento() {
        return departamento;
    }

    String descricao() { // Criação do retorno que dará o visual ao gerar o código
        return super.descricao() +
               "Data de Contratação: " + this.dataContratacao + "\n" + 
               "Salário Base: R$ " + this.salarioBase + "\n" +
               "Departamento: " + this.departamento + "\n";
    }
}

class Cliente extends Pessoa { // Classe de cliente que herda os atributos de classe pessoa, acrescentando email, número do cartão de fidelidade e telefone
    private String email;
    private String numeroCartaoFidelidade;
    private String telefone;

    public Cliente(String nome, String cpf, LocalDate dataNascimento, String email, String numeroCartaoFidelidade, String telefone) {
        super(nome, cpf, dataNascimento); // Utiliza o construtor super pois herda da superclasse Pessoa
        this.email = email;
        this.numeroCartaoFidelidade = numeroCartaoFidelidade;
        this.telefone = telefone;
    }

    public String getEmail() {
        return email;
    }

    public String getNumeroCartaoFidelidade() {
        return numeroCartaoFidelidade;
    }

    public String getTelefone() {
        return telefone;
    }

    String descricao() { // Criação do retorno que dará o visual ao gerar o código
        return super.descricao() +
               "Email: " + this.email + "\n" + 
               "Número do Cartão de Fidelidade: " + this.numeroCartaoFidelidade + "\n" + 
               "Telefone: " + this.telefone + "\n";
    }
}

public class Sistema { 
    public static void main(String[] args) {
        LocalDate dataNascimento = LocalDate.of(1990, 1, 1); // Exemplo de data de nascimento que será utilizado
        LocalDate dataContratacaoVendedor = LocalDate.of(2022, 1, 1); // Exemplo de data de contratação do vendedor que será utilizado

        Vendedor vendedor = new Vendedor("Miguel", "123.456.789-00", dataNascimento, dataContratacaoVendedor, 2500.00, 10.0);
        System.out.println(vendedor.descricao());

        LocalDate dataContratacaoGerente = LocalDate.of(2021, 6, 15); // Exemplo de data de contratação do gerente
        Gerente gerente = new Gerente("Ricardo", "12.345.678-00", dataNascimento, dataContratacaoGerente, 5000.00, "Vendas");
        System.out.println(gerente.descricao());

        Cliente cliente = new Cliente("João", "987.654.321-00", dataNascimento, "joao@facens.br", "123456789", "998224201");
        System.out.println(cliente.descricao());
    }
}
### 🔧 Instalação

* Explicação de como deve ser utilizado o projeto

## 🛠️ Construído com

Ferramentas utilizadas e bibliotecas

* IDE Eclipse

## 📌 Versão

* **Versão 1.0** caso seja atualizado manter a descrição inicial e inserir uma nova linha com descrição da atualização.
* **Versão 1.1** - *Refatoração* *data 09/09/24*

## ✒️ Autores

* João Carlos Ferreira de Araujo RA 248152 -- AC2

