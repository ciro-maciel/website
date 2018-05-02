
# CSS
1. Qual a diferença entre progressive enhancement e graceful degradation? Por que você escolheria um ou outro?

        Progressive Enhancement - aqui projetamos nossa interface com foco nas versoes dos navegadores que nosso publico alvo ira utilizar, algumas vezes podemos deixar alguns recursos de lado. Todavia, com o desenvolvimento continuo teremos atualizacoes progressivas (progressive) para os novos recursos/necessidades da interface.

        Graceful Degradation - desta forma podemos tirar o maximo de proveito para o desenvolvimento de interfaces web, contudo em navegadores mais antigos teremos um pequeno limitar de recurssos/funcionalidades (degradation), mesmo assim, mantemos a interface funcional.

        Minha escolha seria baseada nos analytics/estrategias/requisitos/necessidades/ da aplicacao, pois como vemos, temos um controle granular de "como" implementar as melhorias e aprimoramentos na UI.


2. Como centralizar o bloco segundo o desenho abaixo considerando que as medidas da div.outer são indefinidas?

        Elaborei 03 versoes para a resposta. Disponibilizei em meu site: http://ciro-maciel.me/test/loggi.html 
        ________________________________________
        |                                        |
        |  div.outer                             |
        |          ________200px______           |
        |          |                  |          |
        |     100px|  div.inner       |          |
        |          |                  |          |
        |          |__________________|          |
        |                                        |
        |                                        |
        |________________________________________|


3. Você já usou algum framework de CSS? Qual? Por que?

        Sim, o Twitter Bootstrap. Pela facilidade de uso, pela semantica dos compontes, pela rapida necessidade da prototipagem, pela compatibilidade entre os navegadores, pelo design responsivo, por sua documentacao, pela evolucao programada dos componentes.



4. Você já usou algum pré-processador de CSS? Qual? Por que?

        Como fui o unico desenvolvedor da C37 - CNC (https://github.com/ciro-maciel/style-guide) desde cedo procurei uma forma de automatizar o maximo do processo, pois o controle de versao dos compoentes, a heranca de codigos, a organizacao dos seletores, e bem laborosa no plain CSS.
        
        Por um tempo utilizei less CSS, na epoca seus recursos de heranca perdiam para o Sass. Alem de uma melhor heranca para a componentizacao temos recursos valiosos, como: operations, functions, e junto com Gulp: autoprefixer, minify, um controle de versao com NPM, svg Sprite, concat, etc


5. Você já usou algum pós-processador de JS? Qual? Por que?
        
        Estou utilizando Babel pela disponibilidade de novos e valiosos recursos (novas funcionalidades da liguagem ES6/ES7) que tem impacto direto a agilidade e desenvolvimento do projeto.


6. Como alinhar horizontalmente um bloco com largura definida?

        Acredito que os exemplos funcionem tambem para esta pergunta. http://ciro-maciel.me/test/loggi.html


7. Como você mantem os seletores (classes, ids, etc) de uma base de código que evolui com o tempo? Como faz para remover o que não está sendo usado (e pior, como saber o que está sendo usado)?

        Depois de um tempo desenvolvendo minhas primeiras interfaces tive questoes semelhantes. A solucao que desenvolvi foi:

        - Componentizar toda a interface, definindo primeiramente todos os componentes necessarios para minha interface.
        - Os seletores so trabalhavam dentro do Componente (Scopo) para um determinado tipo, como: 

        button.button
        button.button.disabled
        button.button.success

        div.message.header
        div.message.header.close
        div.message.content

        - Usar o NPM para o controle de versao para a biblioteca de componentes

# Questions
1. Qual a sua experiência com automação de qualidade no front end (ex testes unitários, testes de integração)

        Em minha ultima versao de meu Style Guide (a biblioteca), procuro usar o pensamento API First para a interface, estou uzando StoryBook (seu codigo ja sera a documentacao) devidamente configurado para dar suporte para testes unitarios com JEST, isso utilizando webpack para transpirar tudo em uma biblioteca com controle de versao, baseado em SEMVER (Semantic Versioning).

        Para a applicacao (react), estou consumindo a biblioteca e para cada page tenho um arquivo ".test.js", para todos servicos de testes de integracoes (Jenkins, AWS CodeBuild, circleci, travis CI, APPVeyor, etc.) configuro o package.json chamento "./node_modules/jest-cli/bin/jest.js" no script de test.


1. Qual o bug mais difícil que depurou nos últimos anos?

        Foi depurar um Firmware que eu estava desenvolvendo para um hardware limitado, onde eu estava usando a porta Serial (porta de Debugger) para um ponte de comunicacao com outro dispositivo.


1. Tem alguma experiência com programação funcional? Caso tenha, como ela pode ajudar no desenvolvimento de UI?

        Sim tenho, basicamente todas as aplicacoes Web (Full-Stack, Back-End e Front-End) vao convergir para a programacao funcional, pois como REST lidamos/processamos estados. Desta forma temos uma previsibilidade nos codigos e consecutivamente no sitema.

        Esse tipo de programacao ajuda em todas as etapas de elaboracao, testes e manutencao dos sistemas, pois como disse acima lidamos com estados previsiveis.


1. Como você controla dependências? Você usa um gerenciador de pacotes? Qual? Por quê?

        Sim, utilizo o NPM ou Yarn, pois a componentização do software com o auxlio de Semantic Versioning permite um controle evolucional da solucao como um todo.


1. Tem alguma experiência com Reactive Programming (rx)? Caso tenha, como ela pode ajudar no desenvolvimento de UI?

        Sim, em meus sistemas utilizo rxjs (ReactiveX). Na grande maioria das aplicacoes iremos trabalhar com dados e isso ira acontecer de forma assíncrona.

        Em aplicacoes React, com o auxilio de redux, redux-observable e RxJS temos um controle fino para as solicitacoes dos dados no servidor (Epics), como vemos aqui: https://www.youtube.com/watch?v=AslncyG8whg