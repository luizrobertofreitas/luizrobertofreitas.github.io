---
layout: post
category : [SOA]
tagline: "Definindo o instance name - BPEL"
tags : [BPEL, SOA, Oracle]
---
{% include JB/setup %}

### 1. Introdução

Além de ser uma boa prática (recomendada pela Oracle), algumas vezes é necessário definir o nome da instância para facilitar a visualização e analise no Enterprise Manager do Weblogic.


### 2. Exemplo

**2.1.** Neste exemplo, temos um BPEL chamado `SecondBPELProcess.bpel`:

{% highlight xml %}
  <teste>
    <teste2></teste2>
  </teste>
{% endhighlight %}


![alt text](https://raw.githubusercontent.com/luizrobertofreitas/luizrobertofreitas.github.io/master/_images/2014-11-12-setting-bpel-composite-title/set-composite-title-1.png "Imagem 1")


**2.2.** Adicionamos uma activity `Assign` para atribuir o nome da instância:

![alt text](https://raw.githubusercontent.com/luizrobertofreitas/luizrobertofreitas.github.io/master/_images/2014-11-12-setting-bpel-composite-title/set-composite-title-2.png "Imagem 2")


**2.3.** Criaremos a variável `instanceName` do tipo `string` para atribuir o nome da instância:

![alt text](https://raw.githubusercontent.com/luizrobertofreitas/luizrobertofreitas.github.io/master/_images/2014-11-12-setting-bpel-composite-title/set-composite-title-3.png "Imagem 3")

![alt text](https://raw.githubusercontent.com/luizrobertofreitas/luizrobertofreitas.github.io/master/_images/2014-11-12-setting-bpel-composite-title/set-composite-title-4.png "Imagem 4")

![alt text](https://raw.githubusercontent.com/luizrobertofreitas/luizrobertofreitas.github.io/master/_images/2014-11-12-setting-bpel-composite-title/set-composite-title-5.png "Imagem 5")


**2.4.** Editamos o `assign` chamado: `setCompositeTitle` para adicionar a função `ora:setCompositeInstanceTitle()`:

![alt text](https://raw.githubusercontent.com/luizrobertofreitas/luizrobertofreitas.github.io/master/_images/2014-11-12-setting-bpel-composite-title/set-composite-title-6.png "Imagem 6")


**2.5.** Atribuimos o resultado da função: `ora:setCompositeInstanceTitle('Composite Name')` para a variável `$instanceName`:

![alt text](https://raw.githubusercontent.com/luizrobertofreitas/luizrobertofreitas.github.io/master/_images/2014-11-12-setting-bpel-composite-title/set-composite-title-7.png "Imagem 7")


**2.6.** Após executar uma chamada ao BPEL, podemos constatar na coluna `Name`, o nome da instância:

![alt text](https://raw.githubusercontent.com/luizrobertofreitas/luizrobertofreitas.github.io/master/_images/2014-11-12-setting-bpel-composite-title/set-composite-title-8.png "Imagem 8")


<br/>
#### Até a próxima!!
