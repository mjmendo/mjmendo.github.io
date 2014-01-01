---
layout: post
title:  Escrevendo Posts com Jekyll
date:   2014-01-01 20:00:00
categories: iniciante
---

<p align="right"> "Ensinar é aprender duas vezes". 
</p>

<p align="right">Joseph Joubert</p>
                                                                                   

Para o primeiro post do blog vou falar da ferramenta que usei pra criar este blog.

Jekyll é um gerador de sites estaticos em Ruby e desenvolvido por Tom Preston. Ele pega um diretório de template que contém arquivos de texto brutos em vários formatos, Markdown (ou Textile) e Liquid os converte, e mostra um completo website estático, pronto para publicar em seu servidor web favorito. 

Instalar o Jekyll é muito fácil 

{% highlight bash %}
~ $ gem install jekyll
~ $ jekyll new meublog
~ $ cd meublog
~/myblog $ jekyll serve
# => Now browse to http://localhost:4000
{% endhighlight %}

Para criar um novo post, tudo que você precisa é criar um novo arquivo dentro do diretorio _posts.
Crie o arquivo da seguinte forma:

{% highlight bash %}
YEAR-MONTH-DAY-title.MARKUP
{% endhighlight %}

Pronto! Agora você já tem um novo post no seu blog.

O Jekyll é muito leve e não usa banco de dados ou conteúdo dinâmico gerado em runtime. Você pode hospedar gratuitamente seu blog no GitHub Pages.
