---
layout: post
category : [linux, java]
tagline: "Utilizando make para fazer build de projetos Java"
tags : [java, linux, make, makefile]
---
{% include JB/setup %}

### 1. Introdução

Segundo a própria descrição obtida através do comando `man make`, o propósito do **make** é para determinar automaticamente quais partes de um grande programa/software precisam ser recompiladas e rodar estes comandos para compilar estas partes.

Pensando desta forma, podemos utilizar o make para executar diversas tarefas relacionadas ao desenvolvimento de um programa/software.


### 2. Exemplo

Neste exemplo, vamos criar um arquivo chamado `Hello.java` e inserir o seguinte código complexo (hehe):

```java
public class Hello {
  public static void main(String[] args) {
    System.out.println("Hello World!");
  }
}
```

O próximo passo é criar o arquivo `makefile` para colocar as instruções desejadas para compilação e build.

```makefile
all: step1 step2 step3 step4
step1: ; rm -rf classes && mkdir classes
step2: ; javac Hello.java
step3: ; mv Hello.class classes
step4: ; cd classes && java Hello
```

Após criar os arquivos (.java e makefile), basta executar no shell `make all` automáticamente, o comando **make** irá procurar pelo arquivo **makefile** no diretório e executar as instruções agrupadas no demarcador **all**.

No exemplo, temos outros demarcadores como: **step1**, **step2**... que são agrupados pelo **all**.

Veja o output que contem os logs do **make**, assim como o **Hello World!**


#### Até a próxima!!
