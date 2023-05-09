# Aula 2

Nesta aula, iremos reforçar nosso aprendizado sobre componentes, criando e utilizando um novo componente como vimos na primeira aula.

## Criando um novo componente
A partir daqui iremos ver como criar um componente do zero e renderiza-lô ná pagina para fixar o que aprendemos.
[Clique aqui](./criando_componente.md)


## Observando a Estrutura de um projeto React mais de perto

### Projeto Padronizado de JavaScript

TODO: Falar do Node, pacotes, compartilhamento de código e possibilidade de instalar libs. Arquivo de definição do projeto: `package.json`. É chamado 'Pacote' (do inglês Package) por que é como se chamam os projetos de JS compartilhados entre as pessoas ou empresas.

O que é biblioteca?

### Processo de transformação de código do React

Os navegadores por padrão aceitam somente HTML, CSS e JavaScript puros. Por mais que o React seja bem difundido, os componentes que escrevemos, como por exemplo `<Card></Card>`, não são compreendidos pelos navegadores. Para nós, desenvolvedores de sites, é importante que nosso código funcione em qualquer navegador, seja no celular, tablet, laptop etc. Logo, nosso código precisa ser transformado de React para HTML, CSS e JavaScript puros (e a boa notícia é que já existem ferramentas para fazer essa tradução 🎉)

No nosso caso, o Replit está executando essa transformação pra gente, utilizando algumas ferramentas adicionais. Isso significa que se você quiser tirar este código do Replit e rodar no seu computador sem depender de internet, você precisará instalar ferramentas extras.

Agora que entendemos sobre projetos padronizados de JavaScript e sobre o processo de transformação de código, vamos ver a aplicação de ambos conceitos na prática.

### Estudando os arquivos gerados a partir de um projeto novo

Quando geramos um projeto novo, vamos ver os seguintes arquivos criados para nós:
```
- src/
    - index.js
    - App.jsx
    - App.css
- package.json
- package-lock.json
```

- **`package.json`**: esse arquivo não é especial do React, já que faz parte de um Projeto Padronizado de JavaScript. Vamos mexer nesse arquivo quando precisarmos adicionar bibliotecas ao nosso projeto
- **`package-lock.json`**: é um arquivo gerado automaticamente a partir do `package.json`, também faz parte do padrão de projeto
- **`src/index.jsx`**: este é o primeiro arquivo que seu projeto vai executar. É ele que faz a inicialização e execução do React)
- **`App.jsx`**: um primeiro componente que já vem criado para nós com um conteúdo de exemplo. _App_ significa "Aplicação" e nesse caso pode se referir à uma aplicação mobile ou aplicação no sentido de "website". Podemos remover este componente, ele é opcional. Porém, se removermos este componente, precisamos alterar o `index.jsx` e remover a utilização do componente `<App/>`. É uma boa prática manter o `App` e organizar nosso site aqui dentro
- **`App.css`**: arquivo de estilos do componente `App` que já vem criado para nós
