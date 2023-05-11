# Aula 2

Nesta aula, iremos reforçar nosso aprendizado sobre componentes, criando e utilizando um novo componente como vimos na primeira aula.

## Criando um novo componente
A partir daqui iremos ver como criar um componente do zero e renderiza-lô ná pagina para fixar o que aprendemos.
[Clique aqui](./criando_componente.md)

## Observando a Estrutura de um projeto React mais de perto

### Projeto Padronizado de JavaScript

Todo projeto de JavaScript deve seguir um padrão. Este padrão ajuda na hora de compartilhar nosso código, ou na hora de utilizar códigos que já foram compartilhados por outras pessoas. Esses projetos que podem ser compartilhados também levam o nome de Biblioteca. 

Nosso projeto do Replit com React segue este padrão projeto e o arquivo principal para definição do projeto é o `package.json`. Mais abaixo vamos entrar nos detalhes e no conteúdo desse arquivo.

Vamos entender o que é uma biblioteca de forma prática. Para isto vamos focar nessa parte do site do Núcleo de Tecnologia:
![image](https://github.com/tecMTST/intensivo-react-2023/assets/1435403/fa4f1f99-0eb6-4f6b-b988-34abc43ebe86)

Quando clicamos em cada um desses cards, o seguinte acontece:
![image](https://github.com/tecMTST/intensivo-react-2023/assets/1435403/74d03105-0219-45b2-a0cf-f4a64ae46e94)

Agora faça você mesmo: [vá até o site do Núcleo](https://nucleodetecnologia.com.br/), identifique essa sessão e clique nos cards.

O que acontece quando clicamos? Aparece uma outra janela com o conteúdo daquele card. Além disso, o fundo fica escuro e parece que o conteúdo "salta" e se destaca do conteúdo principal. Esta janela que se destaca é chamada de _Modal_. Você já viu este tipo de janela em outros sites? Provavelmente sim, já que esta janela é muito comum em sites da internet. 

Quando formos fazer o Modal do nosso site, não precisaremos criar o código do zero: vamos utilizar uma **Biblioteca** de Modal que outros programadores já fizeram e vamos encaixar essa bilbioteca no nosso site. Isto só é possível porque as bibliotecas seguem a mesma estrutura e padrão de projeto.

### Processo de transformação de código do React

Os navegadores por padrão aceitam somente HTML, CSS e JavaScript puros. Por mais que o React seja bem difundido, os componentes que escrevemos, como por exemplo `<Card></Card>`, não são compreendidos pelos navegadores. Para nós, desenvolvedores de sites, é importante que nosso código funcione em qualquer navegador, seja no celular, tablet, laptop etc. Logo, nosso código precisa ser transformado de React para HTML, CSS e JavaScript puros (e a boa notícia é que já existem ferramentas para fazer essa tradução 🎉)

No nosso caso, o Replit está executando essa transformação pra gente, utilizando algumas ferramentas adicionais. Isso significa que se você quiser tirar este código do Replit e rodar no seu computador sem depender de internet, você precisará instalar ferramentas extras.

Agora que entendemos sobre projetos padronizados de JavaScript e sobre o processo de transformação de código, vamos ver a aplicação de ambos conceitos na prática.

### Estudando os arquivos gerados a partir de um projeto novo

Agora vamos voltar ao projeto com o componente `BannerInicio` que criamos agora há pouco. Os seguintes arquivos foram criados automaticamente pelo Replit para nós:
```
- public/
- src/
    - index.js
    - App.jsx
    - App.css
- package.json
- package-lock.json
```

- **`public/`**: imagens, documentos e etc. Quaisquer arquivos públicos do nosso site são armazenados aqui. Não utilizaremos esta pasta por enquanto
- **`package.json`**: esse arquivo não é especial do React, já que faz parte de um Projeto Padronizado de JavaScript. Vamos mexer nesse arquivo quando precisarmos adicionar bibliotecas ao nosso projeto
- **`package-lock.json`**: é um arquivo gerado automaticamente a partir do `package.json`, também faz parte do padrão de projeto
- **`src/index.jsx`**: este é o primeiro arquivo que seu projeto vai executar. É ele que faz a inicialização e execução do React
- **`App.css`**: arquivo de estilos do componente `App` que já vem criado para nós
- **`App.jsx`**: um primeiro componente que já vem criado para nós com um conteúdo de exemplo. _App_ significa "Aplicação" e nesse caso pode se referir à uma aplicação mobile ou aplicação no sentido de "website". É uma boa prática manter o `App` e organizar nosso site aqui dentro. Podemos remover este componente, ele é opcional. Porém, se removermos precisamos alterar o `index.jsx` e remover a utilização do `<App/>`. Faça um teste aqui, remova o `<App/>` do `index.jsx` e adicione o componente que foi criado na aula. O que acontece?

### Detalhando o arquivo `package.json`

O `package.json` é o arquivo principal de um projeto padronizado, mesmo que este projeto não utilize React. Ou seja, **todos os projetos de JavaScript utilizam este arquivo de alguma forma**. Por isso é importante entender as principais configurações do `package.json`.

No `package.json` vamos definir: o nome do projeto, nome de autores, a versão, descrição, bibliotecas que utilizaremos e outras definições. 

Vamos começar pelo `.json`. O que isso significa? O formato JSON nada mais é do que um Objeto JavaScript escrito em um arquivo. Um Objeto JavaScript é um tipo de dado que tem chaves e valores. Um exemplo de Objeto representando dados de uma pessoa: `{"nome": "João", "idade": 40}`. Este tipo de dado é perfeito para armazenar configurações do nosso projeto.

Vamos olhar para o código desse arquivo no nosso projeto do Replit, focando em 3 propriedades: 

```js
{
  "name": "react-javascript",  
  ...
  "dependencies": {},          
  "devDependencies": {         
    "react": "^18.2.0",
    ...
  }
}
```

- **`name`**: é o nome do seu projeto, automaticamente configurado como "react-javascript". Pode ser alterado sem problemas.
- **`devDependencies`**: dependências de desenvolvimento. O projeto React precisa ser traduzido para HTML, CSS e JS puros e existem inúmeras bibliotecas que nos auxiliam nessa tarefa. Porém muitas dessas ferramentas **não precisam estar presentes no código final**, depois de traduzido
- **`dependencies`**: são as dependências finais do projeto. Aqui vamos adicionar bibliotecas que se relacionam diretamente com as funcionalidades do nosso site e que **devem estar presentes no código final**, depois de traduzido

Algumas bibliotecas que devemos colocar dentro de `dependencies`:
- **estilos, temas e componentes visuais**. Bibliotecas que adicionam efeitos visuais, temas, cores, posicionamentos e disposição da página, animações, gráficos, Modal e etc
- **manipulação de tempo**. Bibliotecas para lidar com horas e datas, distância entre datas, fuso horário, calendários, formatação de datas
- **matemática**. Bibliotecas para lidar com equações matemáticas e algebricas

... e por aí vai. As opções aqui são muitas. Por via de regra: **em `dependencies` vai toda biblioteca que adiciona alguma funcionalidade que impacta diretamente as pessoas usando**.

Bibliotecas que devemos colocar dentro de `devDependencies`: quaisquer bibliotecas que são utilizadas somente antes ou durante a tradução do React para HTML, CSS e JS.
