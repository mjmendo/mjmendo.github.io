---
layout: post
title:  Virtualenv o que é e por que deveria usar?
date:   2014-01-03 20:00:00
categories: iniciante
---

Eu uso Ubuntu, uma distribuição do Linux, ele já vem
com o python instalado. Para saber qual a versão python
você tem no seu S.O use o seguinte comando:
{% highlight bash %}
~ $ python -V
{% endhighlight %}


Dependendo do projeto que você vai desenvolver em Python você terá
que instalar alguns pacotes e isso é muito fácil nesta linguagem. Mas 
se você não quer comprometer o seu S.O e ter problemas com versões 
você pode usar o virtualenv.

Virtualenv é uma ferramenta para criar ambientes python isolado. Com 
esta ferramenta você pode desenvolver com qualquer versão do Pyhton e sem se perocupar com permissões de usuário.

Para instalar o Virtualenv globalmente basta digitar o comando abaixo:

{% highlight bash %}
~ $ [sudo] pip install virtualenv
{% endhighlight %}

Após a instalação agora é hora de criar o seu ambiente virtual.
Digite virtualenv mais o nome que você deseja para seu ambiente. 

{% highlight bash %}
~ $ virtualenv ENV
{% endhighlight %}

Esse comando irá criar um diretório chamado ENV com mais três diretórios:

    bin – executável do interpretador, o script easy_install e o arquivo activate que será usado para “ativar” o ambiente. Quando o ambiente está “ativo” os executáveis dos aplicativos Python são instalados aqui também.

    lib – a árvore com links simbólicos e/ou cópias de todos os módulos e bibliotecas do Python. Quando esse ambiente está “ativo” os módulos e pacotes serão sempre instalados dentro desse diretório.

O novo virtualenv também vem com o `pip`installer para você instalar pacotes adicionais.

Entre no diretório:

{% highlight bash %}
~$ cd env
{% endhighlight %}

Para ativar o ambiente use:


{% highlight bash %}
~$ source bin/activate
{% endhighlight %}

Agora você pode instalar o que você quiser sem preocupação.





