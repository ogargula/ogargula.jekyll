---
layout: post
comments: true
title: "Falando um pouco sobre Refatoração"
categories: tecnologia programação práticas
---

Todo desenvolvedor já passou pela dúvida de refatorar um código ou não. Se arriscar em uma renomeação de variável, ou na extração de algumas linhas para um novo método um pouco mais coeso. Nem sempre essa é uma tarefa fácil, afinal toda ação causa uma reação e toda escolha traz uma consequência. Mas antes de partir para mudanças é necessário refletir sobre alguns pontos.

## Por que Refatorar?

Manutenibilidade é um ganho instantâneo ao se refatorar código de uma maneira eficiente. Ao pensarmos que uma solução de software é compartilhada entre vários profissionais, não é difícil imaginar que, se cada um escrever da forma como acha que deve sem seguir nenhum padrão, nomeando variáveis de forma displicente e escrevendo métodos gigantes totalmente acoplados, em pouco tempo será impossível manter esse código. Programas bem escritos poupam tempo na busca e resolução de bugs, aumentam a reusabilidade de código e podem ser facilmente estendidos. Logo, o tempo gasto em refatorar código é um investimento e não um custo.

## O que Refatorar?

São vários os sintomas de um código que necessita de refatoração, nem sempre é tão fácil percebê-los, e ainda mais difícil em certos casos mensurar os impactos que as alterações de um método ou classe podem trazer, mas refatorar é necessário. Códigos redundantes, diferentes _ViewModels_ com o mesmo propósito, métodos muito grandes, _Magic Numbers_, variáveis e métodos com nomes incoerentes são bons exemplos de _Bad Smells_ em uma base de código. Este [artigo](https://agilecoachninja.wordpress.com/2017/03/20/code-smells-refactoring/) trás exemplos interessantes com uma abordagem simples para alguns dos sintomas comuns em códigos problemáticos.

## Quando Refatorar?

Sem dúvida esta é uma das questões mais controversas quando se fala em refatoração. "Onde será que isso vai impactar?", "Em quantos lugares vou ter que alterar?", "Resolver isso não faz parte do Bug"... essas são questões que certamente passam pela cabeça de todo dev que se depara com um mal cheiro ao abrir uma classe que precisa de mudanças. Entretanto existem técnicas que amenizam os riscos ao se alterar as linhas de uma solução de software, sem falar em IDEs, Controladores de Versão entre outras ferramentas que auxiliam o profissional do código nessa tarefa. Renomear variáveis, extrair métodos, buscar referências são apenas alguns dos exemplos de funcionalidades que estão distância de click de qualquer programador. Então a resposta para a nossa pergunta é: Sempre que necessário!

## Sugestões

Abaixo seguem algumas sugestões de como abordar um candidato a refatoração,

### Pequenas refatorações

- variáveis locais no escopo de métodos;
- renomear: Variáveis, Métodos privados
- strings concatenadas com '+';
- códigos comentados;
- métodos sem referencia;

**Ação**: Apenas faça!

### Médias refatorações

Alterações que afetam mais de uma classe se mantendo no escopo de um módulo ou camada, desde que não altere a assinatura de métodos.

- Métodos muito grandes;
- Métodos repetidos;
- Lógica em controllers;

Nos casos acima a maior dificuldade é mensurar até onde as mudanças irão impactar, uma boa solução é o _pair programming_, chame um desenvolvedor que já alterou essas classes e conheça a lógica de sistema existente. Isso diminuirá o tempo necessário para a refatoração e evitará a escrita de métodos desnecessários por falta de conhecimento da existência de outros que já supram a mesma necessidade que você pensou.

### Grandes refatorações

Há casos onde as mudanças alcançam fatores externos como o banco de dados, respostas de endpoints, api de módulos inteiros. As vezes para fazer com que o código atenda as regras de negócios, são necessárias mudanças profundas que afetam entidades por exemplo. Erros causados nesse nível podem trazer danos terriveis, por isso é necessário acima de tudo comunicação com o time, tanto para ver se realmente uma mudança nesse patamar é necesária, e caso seja, como ela será feita. Se vai entrar na sprint (caso exista) ou nao, quem irá trabalhar nela. Por experiência própria aconcelho que procedimentos asssim nunca sejam feitos sozinho. Esses casos podem levar tempo para serem resolvidos, então reescrever do zero talvez não seja uma ideia ruim frente aos riscos envolvidos.

Espero que essas ideias sejam um primeiro passo para aqueles que olham aquele codigo feio em suas telas e apenas reclamam do quanto ele é ruim e do quanto o programador que o fez é uma pessoa horrivel. Nunca saberemos a situação a qual a pessoa que codificou estava submetida, logo, nos resta zoar (mas só um pouco rs). E claro, Refatorar.
