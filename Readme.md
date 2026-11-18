# Histórico do projeto — Java (POO)

Registro das atividades de Java feitas no Eclipse entre **29/07 e 19/08**, reescritas a partir das prints do E-Book da atividade do 1º DS.

Autor: Luís Gabriel Mayer Semcovici

## Estrutura

```
src/
├── aula1/      (Carro, TesteCarro)
├── poo/        (Carro, TestarCarro, Produto, ProdutoTestar)
└── exemplo3/   (Aluno, AlunoTestar)
```

---

## 29/07 a 31/07 — Classes, atributos e métodos (pacote `aula1`)

Primeira aula de POO: criação da classe `Carro` com atributos (`nome`, `marca`, `ano`, `vel`) e métodos (`acelerar`, `reduzir`, `buzinar`), e da classe `TesteCarro` para instanciar o objeto e testar os métodos.

**`aula1/Carro.java`**

```java
package aula1;

public class Carro {

    //Atributos
    String nome;
    String marca;
    int ano;
    int vel;

    //Métodos
    void acelerar(int aceleracao) {
        vel += aceleracao;
    }

    void reduzir(int reduzir) {
        vel -= reduzir;
    }

    void buzinar() {
        System.out.println("bibibi");
    }
}
```

**`aula1/TesteCarro.java`**

```java
package aula1;

public class TesteCarro {

    public static void main(String[] args) {

        Carro c1 = new Carro();

        c1.nome="Ferrari";
        c1.marca="Fiat";
        c1.ano=2026;
        c1.vel=60;

        c1.acelerar(10);
        System.out.println("Velocidade: "+ c1.vel + "km/h");

        c1.reduzir(30);
        System.out.println("Velocidade: " + c1.vel + "km/h");

    }

}
```

**Saída no console:**

```
Velocidade: 70km/h
Velocidade: 40km/h
```

---

## 05/08 — Construtores (pacote `poo`)

Classe `Carro` com construtor padrão, construtor com um parâmetro e construtor com dois parâmetros, usando `this`. A classe `TestarCarro` cria três objetos, cada um com um construtor diferente.

**`poo/Carro.java`**

```java
package poo;

public class Carro {
    //Atributos
    String modelo;
    int ano;

    // Construtores
    Carro(){
    }
    Carro(String modelo){
        this.modelo=modelo;
    }
    Carro(String modelo,int ano) {
        this.modelo=modelo;
        this.ano=ano;
    }
}
```

**`poo/TestarCarro.java`**

```java
package poo;

public class TestarCarro {

    public static void main(String[] args) {
        // Construtor padrão
        Carro p1 = new Carro();
        p1.modelo = "Corvette C8 Z06";
        p1.ano = 2023;

        //construtor
        Carro p2 = new Carro("McLaren Senna");
        p2.ano = 2018;

        //construtor com dois parâmetros
        Carro p3 = new Carro("Ferrari", 1996);

        //Objeto
        System.out.println("Modelo: " + p1.modelo + "/" + "ano: " + p1.ano + "/" );

        System.out.println("Modelo: " + p2.modelo + "/" + "ano: " + p2.ano + "/" );

        System.out.println("Modelo: " + p3.modelo + "/" + "ano: " + p3.ano + "/" );

    }

}
```

**Saída no console:**

```
Modelo: Corvette C8 Z06/ano: 2023/
Modelo: McLaren Senna/ano: 2018/
Modelo: Ferrari/ano: 1996/
```

---

## 12/08 — Sobrecarga de construtores com a classe `Produto` (pacote `poo`)

Mesmo conceito aplicado em uma nova classe, `Produto`, com quatro construtores (vazio, com nome, com nome e marca, e com nome, marca e valor). `ProdutoTestar` instancia três produtos.

**`poo/Produto.java`**

```java
package poo;

public class Produto {
    //Atributos
    String nome;
    String marca;
    Float valor;

    //Construtores
    Produto(){
    }
    Produto(String nome) {
        this.nome=nome;
    }
    Produto(String nome,String marca) {
        this.nome = nome;
        this.marca = marca;
    }
    Produto(String nome,String marca,Float valor) {
        this.nome=nome;
        this.marca=marca;
        this.valor=valor;
    }

}
```

**`poo/ProdutoTestar.java`**

```java
package poo;

public class ProdutoTestar {
    public static void main(String[] args) {
        // construtor padrão
        Produto p1 = new Produto();
        p1.nome = "Caneta Preta";
        p1.marca = "Bic";
        p1.valor = 1.50f;

        //construtor de dois parâmetros
        Produto p2 = new Produto("Caneta", "Faber");
        p2.valor = 1.67f;

        // construtor com três parâmetros
        Produto p3 = new Produto("Borracha", "Mercur",1.86f);


        // Objeto
        System.out.println("Nome: " + p1.nome + "/" + "marca:" + p1.marca + "/" + "valor:" + p1.valor + "/");

        System.out.println("Nome: " + p2.nome + "/" + "marca:" + p2.marca + "/" + "valor:" + p2.valor + "/");

        System.out.println("Nome: " + p3.nome + "/" + "marca:" + p3.marca + "/" + "valor:" + p3.valor + "/");

    }
}
```

**Saída no console:**

```
Nome: Caneta Preta/marca:Bic/valor:1.5/
Nome: Caneta/marca:Faber/valor:1.67/
Nome: Borracha/marca:Mercur/valor:1.86/
```

---

## 19/08 — Revisão de `TesteCarro` e introdução à classe `Aluno` (pacotes `aula1` e `exemplo3`)

Revisão do teste do `Carro` da primeira aula (mesmo código de 29/07) e início da classe `Aluno`, usando `setNome`, `getNome` e `setIdade` (encapsulamento com getters e setters). A classe `Aluno` não aparece na print, então foi reconstruída a partir dos métodos usados no teste.

**`aula1/TesteCarro.java`**

```java
package aula1;

public class TesteCarro {

    public static void main(String[] args) {

        Carro c1 = new Carro();

        c1.nome="Ferrari";
        c1.marca="Fiat";
        c1.ano=2026;
        c1.vel=60;

        c1.acelerar(10);
        System.out.println("Velocidade: "+ c1.vel + "km/h");

        c1.reduzir(30);
        System.out.println("Velocidade: " + c1.vel + "km/h");

    }

}
```

**`exemplo3/AlunoTestar.java`**

```java
package exemplo3;

public class AlunoTestar {
    public static void main(String[] args) {
        // Instaciar classe Aluno
        Aluno aluno1 = new Aluno();

        // Aluno aluno1 = "Helio";
        aluno1.setNome("Helio");

        System.out.println(aluno1.getNome());
        aluno1.setIdade(15);

    }

}
```

**`exemplo3/Aluno.java`**

```java
package exemplo3;

// Observação: esta classe não aparece na print (a aba "*Aluno.java" estava aberta, mas sem o conteúdo visível).
// Foi reconstruída a partir dos métodos usados em AlunoTestar (setNome, getNome, setIdade).
public class Aluno {
    private String nome;
    private int idade;

    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public int getIdade() {
        return idade;
    }

    public void setIdade(int idade) {
        this.idade = idade;
    }
}
```

**Saída no console:**

```
Helio
```
