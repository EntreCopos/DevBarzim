---
title: Decisões técnicas 🛠
publishDate: 24 Fev 2024
author: Andre Zorek
description: Todo projeto começa definindo onde e como você quer chegar.
---

Quando definimos com alguma exatidão qual seria o caminho do Barzim como produto, restava decidir como faríamos essa caminhada. Decisões técnicas na arquitetura de um software, independentemente da sua complexidade, são cruciais, podendo ser a diferença entre um produto bem sucedido e algo insustentável a médio e longo prazo. No caso do Barzim essa pressão tinha ainda outro fator: curto ciclo de desenvolvimento. Ainda que o objetivo maior no desenvolvimento de um software comercial seja escalabilidade, previsibilidade, segurança e facilidade de manutenção, quando falamos do *Barzim* era também imprescindível levarmos em consideração o **curtíssimo período** que teríamos para ter esse app em funcionamento, em condição de suportar testes e usuários reais. E ainda há de se salientar, **somos todos iniciantes**. 😅

## Abstrações - apostar no que é prática do mercado

Algumas decisões ja vinham tomadas por nós, é verdade. Trabalhar com React sempre foi uma certeza, visto que além de ser o **foco do nosso** curso, tem sido a principal ferramenta/biblioteca para desenvolvimento de soluções frontend modernas desde sua criação em 2013. Mas fora disso, seriam nossas as decisões que fariam o projeto quebrar ou dar certo.

Para sair na frente e ter condições de focar mais na criação das funcionalidades que queríamos, do que em desenvolver uma solução do zero, uma ideia lógica parecia partir de uma camada de abstração que cuidasse de muitos desses detalhes de implementação por nós: entra em cena, ***Next***.

O mais conhecido e mais usado framework de React entrega uma solução completa que vem desde o backend (server side) até o frontend com tudo que há de mais moderno em React. Além disso, o uso de Typescript em todo o projeto e a integração harmoniosa com várias outras soluções ja existentes para o ecossistema nos deu a segurança de que Next seria o veículo perfeito para seguirmos nosso caminho.

## Bleeding edge  — mas com segurança

O desenvolvimento para web tem avançado de forma muito rápida e no ecossistema React e *Next* isso é especialmente verdadeiro e muito visível (adeus *class components*, adeus *getServerProps*, não sentiremos sua falta ☠️). E ainda que **mudar por mudar** não seja **necessariamente** uma boa decisão, como estávamos começando um projeto do zero, **um quadro em branco**, vimos aqui uma boa oportunidade de abraçar o que há de mais novo e ver como essas soluções ajudariam a moldar ~~(ou quebrar)~~ nosso projeto (spoiler: deu **quase** tudo certo).

### Tailwind

Ok, talvez não seja exatamente "bleeding edge", como se costuma dizer, mas sem dúvida é uma solução que vem ganhando cada vez mais importância e destaque no cenário frontend. Tornou-se um recurso indispensável para muitos desenvolvedores. Seu uso em conjunto com bibliotecas de componentes robustas e confiáveis, como Shadcn, nos permitiu partir de uma base sólida e eficiente, o que é fundamental para o desenvolvimento e entrega de um produto de alta qualidade e grande desempenho. Além disso fizemos uso também o bom e velho CSS (❤️) para solucionar aqueles desafios bem específicos do projeto.

> eu sou do time que ama CSS, me desculpem. 😇
> 

### Prisma ORM

Gestão de bancos de dados é uma tarefa difícil mas necessária. Aqui não seria um bom momento pra buscarmos soluções inacabadas ou imaturas, por isso a solução foi uma abstração muito comum e sólida. Após a modelagem conceitual das estruturas e definição de que iriamos usar PostgresSQL como nosso SGBD, uma escolha natural foi ter o Prisma ORM como camada de interface entre nosso código e o banco de dados. A integração de Prisma foi imensamente facilitada pelo uso de typescript em todo o projeto. Além de *typesafety* ganhamos também um ambiente em que o código fluiu de uma maneira muito simples e natural. O melhor SQL é aquele que você nunca teve que escrever. ✍🏻 

### Server Components e Server Actions

Server components são o futuro de React e portanto, é seguro dizer também, o futuro de boa parte do desenvolvimento de soluções modernas para web. A diferença que faz ter seu código rodando em server-side, devolvendo (às vezes) **HTML puro** para o cliente, é enorme. E é em parte razão do *Barzim* ter um desempenho tão positivo. —insert pic do pagespeed insights

Server actions são uma **novíssima** alternativa de *Next* à tradicional estrutura de uma API com endpoints acessíveis por métodos HTTP. Talvez esse tenha sido o ponto mais **bleeding edge** do projeto. Por baixo dos panos, o que *Next* faz é implementar essas rotas sem que nós tenhamos que manualmente criá-las. Por cima, estamos apenas escrevendo typescript e chamando de client-side nossas funções(actions) em server-side. Mágico. Server actions eram até muito recentemente experimentais, só ganhando o status de *production ready* há alguns meses, mas a perspectiva de conhecer e experimentar uma tecnologia com uma perspectiva tão positiva ainda no seu começo foi muito motivadora. O *Barzim* foi implementado inteiramente em uma combinação de server components e client components que interagem com nosso *backend* através de server actions. Nenhum endpoint de API foi ferido. 💥

## Mão ~~na massa~~ no código

Com todas as decisões técnicas tomadas, a definição pelo uso de soluções mercado como o Next, Tailwind e Prisma ORM, a implementação do Barzim se tornou um processo mais fluído. Cada funcionalidade foi trabalhada de maneira mais eficiente e segura.

A utilização de tecnologias *bleeding edge* como os Server Components e Server Actions também se mostrou uma escolha acertada. Mesmo com o desafio de lidar com funcionalidades ainda recentes (alô, documentação 📄. alô, ChatGPT 🤖) e em - *possível -* constante mudança, a facilidade de implementação desses paradigmas e o ganho em desempenho que trouxeram ao projeto, fez toda a diferença.

Somado a isso, o feedback dos usuários tem sido uma parte crucial deste processo. Através de testes reais, pudemos identificar pontos de melhoria e ajustar nosso produto para melhor atender às necessidades dos usuários. Como o custo de implementação de alterações e novas funcionalidades nesse paradigma é relativamente baixo, este feedback contínuo nos permite fazer do Barzim um produto cada vez melhor ***e em menos tempo***.

A jornada de desenvolvimento do Barzim foi - *até aqui -* desafiadora, mas também muito recompensadora. As decisões técnicas que tomamos no início do projeto se mostraram acertadas e nos ajudaram a criar ***muito rapidamente*** um produto sólido e eficiente. Mal podemos esperar pelos próximos capítulos.