
# Guia do Iniciante: Desbravando o Git

Bem-vindo ao Mundo do Controle de Versão com Git

Se você não conhece o Git, caso você se identifique com alguma dessas frases abaixo, tudo que posso lhe dizer é: Que bom que você está tendo a oportunidade de conhecer, você vai me agradecer, e depois se agradecer por mergulhar nos meandros dessa ferramenta poderosissima.

## O Dev sem Controle de Versionamento:

**"Rapaz, meu computador pifou e perdi todo o código que tinha feito para a próxima atualização!"**

Sem controle de versionamento, os desenvolvedores correm o risco de perder todo o trabalho em caso de falha no hardware ou outros problemas técnicos. Sem um sistema para rastrear e armazenar alterações, todo o progresso pode ser irremediavelmente perdido.

**"Caramba, acabei de quebrar o código da aplicação e agora tenho que refazer tudo manualmente. Que desperdício de tempo!"**
Sem um controle eficaz de versões, os desenvolvedores podem encontrar-se em situações onde precisam refazer o trabalho devido a erros introduzidos durante o desenvolvimento. Isso não apenas consome tempo valioso, mas também pode levar a frustrações e atrasos no projeto.

**"Espera aí, não posso começar a trabalhar nesse arquivo agora. Vou precisar esperar até que Fulano termine suas mudanças, senão podemos acabar sobrescrevendo o trabalho um do outro."**

Sem um sistema de controle de versão, os desenvolvedores podem hesitar em fazer alterações no código por medo de sobrescrever o trabalho de outros colaboradores. Isso pode levar a atrasos no desenvolvimento do projeto e dificuldades na colaboração em equipe.

## O Gerente de Projetos sem Controle de Versionamento:

**"Nossa, quem foi que fez essa alteração no código? Não consigo identificar quem é responsável por isso."**

Sem um controle de versionamento eficaz, os gerentes de projeto podem ter dificuldade em rastrear quem fez quais alterações no código. Isso pode dificultar a identificação de problemas e a responsabilização dos membros da equipe por erros ou más práticas de codificação.

**"Temos múltiplas versões do mesmo arquivo circulando por aí. Como podemos garantir que estamos trabalhando na versão correta?"**

Sem um sistema centralizado de controle de versionamento, os gerentes de projeto podem se deparar com o problema de múltiplas versões do mesmo arquivo, o que pode levar à confusão e inconsistências no desenvolvimento do projeto.

## O Que é o Git?

O Git é muito mais do que apenas uma ferramenta para controlar versões de código. É o guardião das histórias de cada linha de código que você escreve. É o mapa que mostra como seu projeto evoluiu ao longo do tempo. É a ponte que conecta desenvolvedores de todos os cantos do mundo, permitindo que colaborem em projetos de maneira eficiente e harmoniosa.
Por Que o Git é Incrível?

    Flexibilidade Ilimitada: Com o Git, você pode experimentar, ramificar e mesclar suas ideias sem medo de comprometer o trabalho de outros desenvolvedores.

    Controle Total: Nunca mais perca o rastro das mudanças em seu código. O Git permite que você reverta para versões anteriores, compare diferenças e mantenha tudo sob controle.

    Colaboração sem Fronteiras: Esteja você trabalhando com colegas de equipe no mesmo escritório ou contribuindo com projetos de código aberto em todo o mundo, o Git simplifica a colaboração, permitindo que múltiplos desenvolvedores trabalhem juntos de forma eficiente.

## 1. Branching

Se você utiliza o Git como ferramenta de controle de versão para seus softwares, provavelmente já deve ter observado as várias maneiras de como controlar branches de repositórios.

É corriqueiro pessoas utilizarem apenas a branch principal para fazer commits em projetos pessoais, o que não é errado, pois quando estamos trabalhando sozinhos é relativamente tranquilo de se controlar tudo em um branch só, embora eu ainda sim recomendo que vocês tenham uma organização básica nos projetos pessoais de vocês e acima de tudo, entendam o porque o git é tão importante.

Mas não em projetos de grandes proporções onde existem vários desenvolvedores realizando alterações nesses repositórios constantemente.

![Big Brain Mode](../assets/NoPR.png)

O Git Flow nada mais é que um modelo de contribuições que é amplamente utilizado para o desenvolvimento colaborativo, e ele se baseia em duas branchs principais:

![Git Flow](../assets/gitflow.png)
````
master -> Que representa o estado atual de todos os processos correntes na produção
develop -> Derivada da master, é a branch onde iremos enviar nossas alterações durante as semanas, para que no final, após todos os testes necessários, realizemos o merge na master.
````

### 1.1. Nomenclatura para Branchs e commits

Neste repositório nós organizamos as contribuições baseadas: no tipo de alteração, o processo e a data, sendo:

Uma branch de alteração:
````
update/processo21_01-04-24
````
Uma branch de correção de bugs:
````
bugfix/processo21_01-04-24
````


### 1.2. Quickstart

Sempre que lhe for passado uma alteração pra ser realizada, o processo é sempre o mesmo:

A Branch Master sempre será atualizada com os processos correntes da produção e a develop irá persistir essas alterações, então você deve:

1. Voltar pra branch develop. (Caso não saiba em qual branch você esta: git status)
````
-> git checkout develop
````
2. Puxar todas as alterações do repositório remoto.
````
-> git pull
````

3. Agora que sua maquina local está atualizada e persistindo os dados do repositório remoto, você cria uma nova branch.
````
-> git checkout -b "update/processo23_15-04-24"
````
4. Você irá realizar todas as alterações nessa branch, e quando finalizar:

Você pode rodar:
````
-> git status (Isso irá lhe permitir ver tudo que foi identificado como alterado, removido e afins)
````

````
-> git add . (Pra adicionar todos os arquivos que sofreram alterações pra serem inseridos no commit)
````
ou
````
-> git add caminho/do/arquivo.js (Pra adicionar arquivos especificos)
````

5. Quando inserir todos os arquivos que deseja enviar para o commit, faça:
````
-> git commit -m "update: Mensagem do commit"
````
6. Por ultimo, envie as alterações pro servidor remoto:
````
-> git push (O primeiro commit de uma nova branch o comando é diferente: git push --set-upstream origin update/processo23_15-04-24)
