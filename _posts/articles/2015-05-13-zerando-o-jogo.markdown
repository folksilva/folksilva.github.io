---
layout: post
title: "Zerando O Jogo"
modified:
categories: articles
excerpt: Como a Data Science pode ajudar a bola entrar no gol
tags: [
    "datascy",
    "devcamp",
    "apresentações"
]
image:
  feature: "ZerandoJogo/ZerandoJogo-0.jpg"
  thumb: "ZerandoJogo/ZerandoJogoThumb.png"
date: 2015-05-13T19:25:04+00:00
comments: true
share: true
published: true
---


Olá pessoal!

No dia 15 de maio apresentei esses slides no [Devcamp 2015][devcamp], o objetivo
foi introduzir rapidamente os conceitos da teoria dos jogos e da data science e
demonstrar como ela pode ser usada no mundo do futebol para ajudar na busca de
melhores resultados.

Se não pôde participar do Devcamp veja agora uma transcrição da apresentação.

<iframe src="https://www.slideshare.net/slideshow/embed_code/key/yXscwNp2ZETiQo"
  width="560" height="430" frameborder="0" marginwidth="0" marginheight="0" 
  scrolling="no"></iframe>

<!-- Begin MailChimp Signup Form -->
<div id="mc_embed_signup">
<form action="//github.us10.list-manage.com/subscribe/post?u=5853bde8ed9c322f380751264&amp;id=78cb1f1eb4" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
  <div id="mc_embed_signup_scroll">
	  <label for="mce-EMAIL">Deixe seu e-mail para receber meus artigos sobre desenvolvimento, aprendizado e produtividade.</label>
  	<div class="clear">
  	  <input type="email" value="" name="EMAIL" class="email" id="mce-EMAIL" placeholder="email address" required>
  	  <input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe" class="button">
  	</div>
    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
    <div style="position: absolute; left: -5000px;">
      <input type="text" name="b_5853bde8ed9c322f380751264_78cb1f1eb4" tabindex="-1" value="">
    </div>
  </div>
</form>
</div>
<!--End mc_embed_signup-->

## Zerando o Jogo


![CIFUT]({{site.url}}/images/ZerandoJogo/ZerandoJogo-2.jpg)

Eu sou o Luiz, desenvolvedor no Corinthians, faço parte da equipe do CIFUT, o
Centro de Inteligência do Futebol. A equipe é formada por seis analistas de
desempenho, que acompanham e analisam muita informação sobre
praticamente tudo no futebol, eles são realmente muito bons no que fazem,
minha visão sobre o futebol mudou completamente e aposto que, se qualquer 
torcedor comum parar para conversar 10 minutos com um deles, vai ver que futebol
é muito mais complexo do que podemos imaginar. O meu trabalho lá é ajudar a
simplificar a captura e o processamento das informações para gerar o
conhecimento que é transmitido para a comissão e para os jogadores.

![Goool!!!]({{site.url}}/images/ZerandoJogo/ZerandoJogo-5.jpg)

O gol, o momento que todos esperam aflitos, com o coração na mão, e quando
acontece parece que todo o peso do mundo sai das suas costas, naqueles
segundos suas preocupações desaparecem e uma alegria toma seu coração. Mas
por que? Por que o gol tem esse efeito sobre nós?

Simples, por que ele é um evento extremamente raro, tão simples mas muito
difícil de conquistar, é essa raridade que faz o futebol ser o esporte mais
praticado no mundo e que enche estádios, todos querem ver a raridade
acontecer diante de seus olhos.

![50% habilidade, 50% acaso]({{site.url}}/images/ZerandoJogo/ZerandoJogo-7.jpg)

No livro [**Os Números do Jogo**][numeros-jogo], Chris Anderson e David Sally
mostram que o motivo dos gols em 50% das vezes é graças a habilidade dos
jogadores e nas outras 50% por acaso, como um rolar de dados.

![Milhões em habilidade]({{site.url}}/images/ZerandoJogo/ZerandoJogo-9.jpg)

Esse é o motivo para os clubes do mundo inteiro investirem milhões contratando
os melhores jogadores, para garantir que seus 50% de habilidade sejam suficientes
para aumentar as chances de vitória.

Veja o exemplo do [Cristiano Ronaldo][zerando-jogo-01], um dos maiores salários
no futebol.

![Café com pão]({{site.url}}/images/ZerandoJogo/ZerandoJogo-10.jpg)

Investir milhões não é a melhor estratégia, ainda mais quando se tem grandes
dívidas e se vive em um país onde um único dolar vale mais que um pão na chapa
com cafézinho, precisamos encontrar outra opção.

A melhor forma de encontrar uma resposta para esse problema é entender o jogo,
desmembrar toda a sua complexidade, e melhor forma de fazer isso é usando a
teoria dos jogos.

##Teoria dos Jogos e Data Science

![Teoria dos Jogos]({{site.url}}/images/ZerandoJogo/ZerandoJogo-12.jpg)

Talvez você já tenha assistido o filme
[**Uma mente brilhante *(A Beautiful Mind)***][mente-brilhante], ele mostra a
história de John Nash, um gênio matemático, que ajudou a popularizar a teoria
dos jogos, recomendo que assista o filme.

Em breve vamos ver como o John Nash vai nos ajudar.

A [teoria dos jogos][zerando-jogo-02] é um ramo da matemática que estuda as situações
estratégicas entre jogadores, considera as cooperações e concorrências e tem o
objetivo de ajudar a entender as estratégias que podem trazer o melhor retorno
para os jogadores.

![Exemplo no futebol]({{site.url}}/images/ZerandoJogo/ZerandoJogo-15.jpg)

Agora um exemplo da teoria dos jogos dentro do futebol, o pênalti. Na forma mais
simples, são dois jogadores interagindo, ambos tem que tomar uma decisão aleatória
no momento que o juiz apita.

![O jogo do penalti]({{site.url}}/images/ZerandoJogo/ZerandoJogo-18.jpg)

O goleiro tem que escolher um lado para defender e o batedor um lado para atacar.
Se o goleiro escolher um lado qualquer diferente do lado do batedor temos um gol,
o goleiro perde e o batedor ganha. Já se o goleiro e o batedor escolherem o mesmo
lado temos uma defesa. Bem simples aparentemente né?

![Decisão estratégica]({{site.url}}/images/ZerandoJogo/ZerandoJogo-19.jpg)

E se o goleiro souber em qual lado o batedor provavelmente vai chutar antes do
juiz apitar? A decisão não vai ser mais aleatória e sim estratégica. O mesmo vale
para o batedor, se ele souber para qual lado o goleiro provavelmente vai pular a
habilidade dele é potencializada e as chances de fazer o gol são maiores.

Conseguir essa informação pode definir a equipe campeã.

![Na vida real não é tão simples]({{site.url}}/images/ZerandoJogo/ZerandoJogo-20.jpg)

Só saber o que o adversário provavelmente vai fazer não é garantia, ele pode
saber que você tem essa informação e então mudar de estratégia, agora temos
um problema, e nosso amigo John Nash vai nos ajudar.

![Respostas com teorias de jogos]({{site.url}}/images/ZerandoJogo/ZerandoJogo-24.jpg)

Aplicando os conceitos da teoria dos jogos conseguimos chegar em três respostas
básicas:

* **A melhor possível:** Desconsiderando que o adiversário pode saber sobre a sua
estratégia, essa é a opção que te dá a melhor probabilidade de vitória;
* **A pior possível:** Entender o que você tem que evitar ao máximo fazer muitas
vezes é mais importante do que saber o que fazer, essa é a opção que aumentam ao
máximo as chances do adversário;
* **A opção equilibrada:** Essa é a opção que considera que você e o adversário
buscaram as melhores opções, na matemática isso é chamado de *equilíbrio de Nash*,
e te dá a melhor resposta com as menores consequências negativas e as melhores
positivas.

O penalti é um jogo muito simples, um jogador habilidoso é capaz de encontrar
sozinho uma resposta para o problema apenas com algumas informações sobre o
adversário. Porém, para a maioria dos casos precisamos de informação, muita 
informação, aí entra a Data Science.

![Data Science]({{site.url}}/images/ZerandoJogo/ZerandoJogo-26.jpg)

De forma genérica, a [Data Science][zerando-jogo-03], pode ser definida como a extração de
conhecimento da informação, utilizando a metodologia científica. Engloba, além
da tecnologia da informação, a matemática e a estatística.

A Data Science existe a muito tempo e é usada em muitas áreas, por exemplo na 
biologia para entender a evolução, na medicina para entender e prever epidemias 
e atualmente no comércio para recomendar os produtos que você provavelmente vai 
gostar mais.

##O ciclo da Data Science

![O ciclo da data science]({{site.url}}/images/ZerandoJogo/ZerandoJogo-37.jpg)

A Data Science tem um fluxo básico para seguir, que serve de guia para criar seus
projetos de ciência de dados.

####Obter Informações do Mundo Real

Inicialmente você precisa descobrir formas de capturar os dados do mundo real
para que você possa analisar depois, os dados podem vir de qualquer jeito, de
múltiplos sistemas e ambientes, então você também precisa tratá-los para
conseguir trabalhar com eles.

####Encontrar Perguntas para Responder

Quando você tem dados organizados e limpos, você pode separar uma amostra e
procurar por padrões de comportamento e relacionamentos, nessa fase você
começa a formar hipóteses sobre o mundo real, usando como base seu
conhecimento sobre o que está estudando e as pistas que os dados te
apresentam.

####Testar as Respostas das Perguntas

Com suas hipóteses formadas chegou a hora de experimentá-las, usando a maior
concentração de dados disponível você consegue confirmar ou descartar suas perguntas
e formular novas, nessa fase o volume de dados vai te dar mais precisão nos resultados,
então quanto mais big melhor.

> A computação e a internet permitem trabalhar com mais informações, de um jeito
que nunca foi possível antes na história da humanidade.

Essa é a diferença da Data Science para os estudos científicos tradicionais, a computação
e a internet te permitem trabalhar com muito mais informações, espalhadas pelo
mundo todo, de forma rápida e eficiente.

####Preparar para Reprodução

Com seus modelos testados e confirmados você não precisa mais ficar refazendo todos
os testes manualmente, nesse passo podemos construir modelos reproduzíveis e
ensinar as máquinas a fazer o trabalho matemático pesado pela gente.

####Criar Produtos de Dados

O produto final pode ser um dashboard com gráficos interativos, um relatório impresso
ou até uma planilha no Excel.

Talvez esse seja o passo mais importante, se não soubermos transmitir o conhecimento
produzido, todos os passos anteriores terão sido em vão, você pode ter a rede de
computadores mais poderosa do mundo, capaz de processar terabytes de dados por
segundo, mas se a visualização do resultado passar a mensagem errada, todo o seu
estudo estará comprometido.

####Evoluir com o Mundo Real

Como tudo no universo, os dados estão em constante evolução, é necessário reanalisar
os dados constantemente para formular novas hipóteses e encontrar novas pistas que te
colocarão a frente de todos os concorrentes, sempre alguma coisa passa desapercebido
e pode ser detectada numa segunda, terceira ou milésima passada de olhos.

<!-- Begin MailChimp Signup Form -->
<div id="mc_embed_signup">
<form action="//github.us10.list-manage.com/subscribe/post?u=5853bde8ed9c322f380751264&amp;id=78cb1f1eb4" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
  <div id="mc_embed_signup_scroll">
	  <label for="mce-EMAIL">Como está sua leitura? Deixe seu e-mail para receber mais.</label>
  	<div class="clear">
  	  <input type="email" value="" name="EMAIL" class="email" id="mce-EMAIL" placeholder="email address" required>
  	  <input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe" class="button">
  	</div>
    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
    <div style="position: absolute; left: -5000px;">
      <input type="text" name="b_5853bde8ed9c322f380751264_78cb1f1eb4" tabindex="-1" value="">
    </div>
  </div>
</form>
</div>
<!--End mc_embed_signup-->

## Data Science no Corinthians

![Data Science no Corinthians]({{site.url}}/images/ZerandoJogo/ZerandoJogo-38.jpg)

Agora vou mostrar um pouco de como funciona o Centro de Inteligência do Futebol 
(CIFUT). O jogo é muito mais do que os minutos entre o apito inicial e o final do
jogo, cada um é um evento gigantesco com uma rotina exaustiva que começa muito
antes do jogo e continua depois de ter terminado.

<figure class="half">
  <img src="/images/ZerandoJogo/ZerandoJogo-40.jpg">
  <img src="/images/ZerandoJogo/ZerandoJogo-41.jpg">
</figure>

Alguns dias antes do jogo, a equipe analisa o passado da equipe adversária, seus
pontos fortes, suas fraquezas. Quando necessário analisa profundamente um jogador,
assistindo horas e mais horas de jogo atrás de jogo, até definir um padrão
comportamental do adversário.

Todas as informações são repassadas para a comissão técnica e para os jogadores antes
do jogo, para que conheçam os possíveis problemas e oportunidades.

<figure class="half">
  <img src="/images/ZerandoJogo/ZerandoJogo-42.jpg">
  <img src="/images/ZerandoJogo/ZerandoJogo-43.jpg">
</figure>

Durante o jogo a equipe coleta muita informação, utilizando iPads e fazendo marcações
em tempo real sobre tudo no jogo. Todos os passes, toques na bola e até
comportamentos dos jogadores longe da bola é registrado.

Ainda no jogo algumas informações são apresentadas para a comissão, informações que
ajudam na preparação para o segundo tempo e dão uma visão geral do que está
acontecendo. Infelizmente, o regulamento dos jogos não permite que essa informação
vá em tempo real para eles na beira do campo e acredito que está certo, pensando em
outras equipes menores o acesso a informação em tempo real seria uma vantagem
injusta.

<figure class="half">
  <img src="/images/ZerandoJogo/ZerandoJogo-44.jpg">
  <img src="/images/ZerandoJogo/ZerandoJogo-48.jpg">
</figure>

Após o jogo o trabalho continua, a análise feita durante o jogo é revista e aprofundada,
os erros e acertos da equipe são separados para que a comissão trate com cada jogador
individualmente.

O objetivo é entender o que aconteceu de certo e errado nos mínimos detalhes.

As informações coletadas antes, durante e depois do jogo são armazenadas, analisadas
e viram relatórios, vários relatórios. Alguns on-line, outros impressos, com o objetivo de
levar a informação o mais simples, direta e corretamente possível para quem precisa.

Como exemplo, existem relatórios interativos com informações sobre todos os gols,
pênaltis e outros lances dentro de cada jogo.


##Como Formar uma Equipe de Data Science

No Corinthians, o CIFUT não é oficialmente uma equipe de Data Science, embora tenha
esse papel. Agora vou mostrar o que é necessário em uma equipe de Data Science
completa.

![Habilidades Data Science]({{site.url}}/images/ZerandoJogo/ZerandoJogo-53.jpg)

Primeiro, a habilidade na ciência da computação, o que dá poder à Data Science é
o uso inteligente dos recursos computacionais existentes, precisamos de alguém 
capaz de transformar as hipóteses em modelos reproduzíveis e que consiga 
desenvolver formas de manipular grandes volumes de dados.

Precisamos também de conhecimento específico na área de estudo, para conseguir
formular as hipóteses e interpretar os resultados da melhor forma possível, a qualidade
da informação produzida depende da qualidade do conhecimento da equipe na área
estudada.

Por último, conhecimento matemático e estatístico. Conhecer o ambiente e saber usar a
tecnologia a favor não é suficiente, é preciso saber como extrair conhecimento dos
dados usando matemática, ela é o elo que une a computação com o conhecimento
específico.

As três habilidades são muito importantes para formar a Data Science.
Usar o poder computacional apenas aplicando o conhecimento específico pode produzir
conhecimento incorreto, a ciência tradicional combina apenas o conhecimento
específico e a matemática, o Machine Learning não precisa necessariamente de um
ramo científico para funcionar, só precisa de matemática e poder computacional.

Para entender melhor essas habilidades, leia o excelente artigo [*The first rule
of data science*][zerando-jogo-04] publicado na The Berkeley Science Review.

##Como Aprender Mais?

Quem se interessou por esse ramo, recomendo que se aprofunde, isso tende a ser 
uma área muito concorrida no futuro breve.

Vou mostrar agora algumas formas para nós desenvolvedores nos aprofundarmos em 
algumas áreas da Data Science

![Estatística]({{site.url}}/images/ZerandoJogo/ZerandoJogo-57.jpg)

Primeiro estatística, talvez a área com o maior déficit para nós.

* [Think Stats][zerando-jogo-05]: Esse livro de Allen Downey mostra como usar 
Python na estatística, ele está disponível gratuitamente para ler on-line ou
também pode ser comprado na Amazon.
* [Statistics, Making sense of Data][zerando-jogo-06]: Esse curso da Universidade
de Toronto está disponível gratuitamente no Coursera, introduz a estatística com
foco para programadores.
* [R][zerando-jogo-07]: Essa é uma linguagem de programação projetada por 
estatísticos, repleta de ferramentas e funcionalidades que ajudam na exploração
de dados e em todos os aspectos da ciência de dados.

![Machine Learning]({{site.url}}/images/ZerandoJogo/ZerandoJogo-62.jpg)

Machine Learning é, pelo menos para mim, uma das áreas de estudo mais fascinantes
da computação hoje.

* [A Programmer's Guide to Data Mining][zerando-jogo-08]: Esse guia orienta nós
programadores em como praticar a arte de minerar dados utilizando Python, disponível
gratuitamente on-line.
* [Machine Learning][zerando-jogo-09]: Esse curso da universidade de Stanford também
está disponível gratuitamente no Coursera, ele é um curso sob demanda, então você
pode começar e terminar a qualquer momento, sem a necessidade de esperar a formação de turma.
* [Python][zerando-jogo-10]: E claro não poderia deixar de falar da minha
linguagem de programação favorita, a maioria dos projetos de Machine Learning
provavelmente utilizam Python em alguma parte, é uma linguagem muito versátil e simples,
fiquem ligados aqui no meu site que em breve vou falar mais sobre Python e suas funcionalidades.

![Visualização]({{site.url}}/images/ZerandoJogo/ZerandoJogo-66.jpg)

Eu acredito que todos programadores, matemáticos e humanos deveriam ter pelo 
menos um conhecimento básico nos conceitos de design, isso se prova na hora gerar
uma visualização para os seus resultados.

* [The Visual Display of Quantitative Information][zerando-jogo-11]: Esse livro
de Edward Tufte ensina as melhores formas de apresentar visualmente dados 
quantitativos, uma excelente leitura para aprender novas formas de fazer a
informação chegar da melhor forma ao destino final.
* [Data Visualization - *Stat645*][zerando-jogo-12]: A universidade do Rice
disponíbiliza um curso gratuito focado na apresentação de dados.
* [D3.js][zerando-jogo-13]: Para aproveitar o poder do HTML5 para produzir
visualizações recomendo o poderosíssimo D3, ele permite gerar visualizações
fantásticas e possui até um port para Python.

![Computação em Escala]({{site.url}}/images/ZerandoJogo/ZerandoJogo-70.jpg)

A computação em nuvem permitiuque um pequeno investimento fosse suficiente para 
construir grandes redes computacionais, isso abriu as portas para o desenvolvimento
de programas que rodam simultaneamente em vários computadores.

* [Hadoop - The Definitive Guide][zerando-jogo-14]: Na crista da onda da computação
em escala vem surfando o elefante amarelo do Hadoop, esse livro provavelmente fica
na cabeceira da cama daqueles que estão se aprofundando nesse mundo, e se esse é o
seu objetivo ele é um excelente começo.
* [Web Intelligence and Big Data][zerando-jogo-15]: Esse curso da Indian Institute
of Technology Delhi dá uma visão completa da computação em escala e Big Data.
* [Spark][zerando-jogo-16]: Esse projeto da Fundação Apache promete facilitar o
uso de todo o poder da computação em escala com muito mais agilidade e eficiência.

##A Complexidade do Futebol

![Zerar o jogo]({{site.url}}/images/ZerandoJogo/ZerandoJogo-72.jpg)

Será que é possível zerar o futebol? Encontrar uma estratégia perfeita que vai 
garantir a vitória em todos os jogos?

Sim, nós do CIFUT acreditamos que é possível! Mas sabemos que é muito difícil.
Não foi o caso da seleção da Austrália que fez 31 a 0 contra a Samoa Americana 
([saiba mais aqui][zerando-jogo-17]) nas eliminatórias da copa de 2002, isso foi
uma combinação da habilidade da seleção australiana, da falta de habilidade da 
Samoa e do acaso que deu uma vantagem insuperável para os vencedores da partida.

Existem obstáculos gigantescos que ainda nos impedem de zerar o jogo.

####Como saber se temos dados suficientes?

Não temos como saber se os dados coletados são suficientes para nos permitir 
formar uma hipótese boa o suficiente. Talvez seja necessário coletar informações
que nem sabemos que existem no mommento do jogo.

####Como saber se a pergunta feita vai dar a resposta que precisamos?

E com as hipóteses que conseguirmos formar não podemos garantir também que o 
resultado produzido vai nos dar algum retorno real. Anos de estudo podem nos levar
a mais questionamentos sobre o futebol com respostas não conclusivas.

<iframe width="560" height="315" src="https://www.youtube.com/embed/8oDA4uNIKhw"
  frameborder="0" allowfullscreen></iframe>

> Não sei o que aconteceu ou se aconteceu não tô sabendo.
> Mas futebol é isso que aconteceu, porque eu não sei o que aconteceu.

Tudo isso porque o futebol é extremamente complexo e mutável, muito difícil de 
controlar e com uma cultura que descarta o uso da matemática aplicada.

<figure class="third">
  <img src="/images/ZerandoJogo/ZerandoJogo-77.jpg">
  <img src="/images/ZerandoJogo/ZerandoJogo-78.jpg">
  <img src="/images/ZerandoJogo/ZerandoJogo-79.jpg">
</figure>

O cenário atual da Data Science no futebol tem um desequilíbrio bem nítido.

Por um lado temos muito conhecimento específico nas comissões técnicas dos clubes
no mundo inteiro.

Existem várias empresas lucrando por usar tecnologias avançadas para entregar 
informações sobre futebol, embora sejam informações básicas.

O elo fraco está na inexistência de modelos matemáticos de qualidade, os modelos 
que existem são muito básicos, são somas e subtrações se comparados com a 
evolução dos modelos em outras modalidades esportivas e ramos da ciência. 
Isso devido principalmente a grande variedade de tipos de evento dentro de um 
jogo e na escassez desses eventos para analisar e testar.

##Uma Solução

![Solução]({{site.url}}/images/ZerandoJogo/ZerandoJogo-81.jpg)

Existe uma solução para nos ajudar a zerar o jogo?

Acredito que sim, podemos usar o poder da tecnologia para simular os eventos 
raros e produzir modelos matemáticos mais confiáveis. Da mesma forma que os 
cientistas constroem cenários artificiais para simular e estudar a colisão de 
galáxias ou outros eventos extremamente raros.

Não é uma tarefa simples, mas a equipe do CIFUT está cada dia mais preparada para
atingir esse objetivo.

##Concluindo

Você viu nesse artigo uma transcrição da minha apresentação no Devcamp 2015, espero
ter mostrado claramente como a teoria dos jogos e a Data Science podem ser usadas 
para ajudar a entender eventos raros, também espero que as referências que apresentei
aqui te ajudem na sua jornada de aprendizado, no final esse foi meu objetivo principal,
quanto mais especialistas existirem na Data Science mais poderosa e acessível ela
se torna.

Deixe o seu comentário dizendo o que achou, compartilhe para os seus amigos e deixe
o seu e-mail no formulário abaixo para receber mais artigos sobre desenvolvimento,
aprendizado e produtividade.

Nos vemos em breve, um grande abraço!

<!-- Begin MailChimp Signup Form -->
<div id="mc_embed_signup">
<form action="//github.us10.list-manage.com/subscribe/post?u=5853bde8ed9c322f380751264&amp;id=78cb1f1eb4" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
  <div id="mc_embed_signup_scroll">
	  <label for="mce-EMAIL">Deixe seu e-mail para receber mais novidades.</label>
  	<div class="clear">
  	  <input type="email" value="" name="EMAIL" class="email" id="mce-EMAIL" placeholder="email address" required>
  	  <input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe" class="button">
  	</div>
    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
    <div style="position: absolute; left: -5000px;">
      <input type="text" name="b_5853bde8ed9c322f380751264_78cb1f1eb4" tabindex="-1" value="">
    </div>
  </div>
</form>
</div>
<!--End mc_embed_signup-->


[devcamp]: http://www.devcamp.com.br/
[numeros-jogo]: http://oferta.vc/7M41
[zerando-jogo-01]: http://j.mp/zerando-jogo-01
[mente-brilhante]: http://www.adorocinema.com/filmes/filme-28384/
[zerando-jogo-02]: http://j.mp/zerando-jogo-02
[zerando-jogo-03]: http://j.mp/zerando-jogo-03
[zerando-jogo-04]: http://j.mp/zerando-jogo-04
[zerando-jogo-05]: http://j.mp/zerando-jogo-05
[zerando-jogo-06]: http://j.mp/zerando-jogo-06
[zerando-jogo-07]: http://j.mp/zerando-jogo-07
[zerando-jogo-08]: http://j.mp/zerando-jogo-08
[zerando-jogo-09]: http://j.mp/zerando-jogo-09
[zerando-jogo-10]: http://j.mp/zerando-jogo-10
[zerando-jogo-11]: http://j.mp/zerando-jogo-11
[zerando-jogo-12]: http://j.mp/zerando-jogo-12
[zerando-jogo-13]: http://j.mp/zerando-jogo-13
[zerando-jogo-14]: http://j.mp/zerando-jogo-14
[zerando-jogo-15]: http://j.mp/zerando-jogo-15
[zerando-jogo-16]: http://j.mp/zerando-jogo-16
[zerando-jogo-17]: http://j.mp/zerando-jogo-17
[zerando-jogo-18]: http://j.mp/zerando-jogo-18