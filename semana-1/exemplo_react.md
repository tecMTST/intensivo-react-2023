# Aula 01 - Começando com React
Crie um novo Replit utilizando [este link](https://replit.com/@replit/React-Javascript). Para mais detalhes em como criar o Replit, [acesse nosso guia](./como_criar_um_replit_em_react.md).

## Passo 1 - Criando um novo arquivo para nosso componente

No Replit, localize os arquivos do seu projeto e a pasta `src`. Ao lado desta pasta, clique nos três pontinhos e selecione "Add file" (Adicionar Arquivo):

![image](https://user-images.githubusercontent.com/1435403/236091782-5640e1b3-84b1-477c-9090-85e7905addfa.png)

O nome do novo arquivo deve ser **Card.jsx**:

![image](https://user-images.githubusercontent.com/1435403/236092074-ac7427f1-0e22-41b5-956b-26dd3383054f.png)

Quando criamos arquivos Javascript, colocamos `.js` no final. Mas o nome do nosso arquivo tem `jsx` no final, indicando que ele é um arquivo do React.

## Passo 2 - Criando o nosso primeiro Componente react

No novo arquivo `Card.jsx` criado, vamos colocar o seguinte código:

```jsx
export default function Card() {
  return (
    <div>
      <p>
        Meu Card
      </p>
    </div>
  )
}
```

A primeira coisa que podemos observar neste código é que aparentemente temos HTML (tags `div` e `p`) dentro de uma `function`, que faz parte do Javascript. O React torna possível a combinação de HTML com Javascript em um mesmo arquivo. Vamos quebrar esse código acima para entender todas as partes:

### Parte 1: Javascript

Vamos começar pela definição da função chamada `Card`. O pedaço do código que veremos abaixo não tem novidade:
```js
function Card() {
  return ...
}
```

Neste pedaço do código, estamos definindo uma função chamada `Card` e dentro dela existe algo sendo retornado.

### Parte 2: HTML dentro do Javascript

Agora vamos olhar o que vem depois do `return` no nosso arquivo `Card.jsx`:
```html
<div>
  <p>
    Meu Card
  </p>
</div>
```

Este código acima também não tem novidade, estamos utilizando uma tag `div` que tem dentro dela uma tag `p` que, por sua vez, tem o texto "Meu Card". 

A novidade, porém, é que este código está sendo utilizado dentro do Javascript. Mais que isso, **este código HTML está servindo como retorno de uma função Javascript** (pois vem logo após a palavra `return` no código). Isso significa que quando utilizarmos o componente `Card`, o React vai nos dar este código HTML como resultado.

### Parte 3: Exportar variáveis ou funções

Vamos analisar agora a ultima parte do código:

```
export default ...
```

Utilizamos o `export default` no Javascript quando desejamos que uma variável ou função de um arquivo esteja disponível para uso em outro arquivo. Precisamos dessa funcionalidade pois cada componente terá seu próprio arquivo. Não se preocupe se não entendeu o conceito agora, vamos explorar esta funcionalidade mais a fundo durante o intensivo.

## Passo 3 - Utilizando o componente criado

Já temos o nosso primeiro componente React 🎉. Lembra da analogia que fizemos com pecinhas de Lego? Agora o componente Card é como se fosse uma pecinha de Lego, pronta para ser encaixada. Precisamos encaixar essa peça para podermos ver o resultado na tela. O arquivo `App.jsx` é o local onde vamos montar nosso site e encaixar nossas pecinhas.

### Entendendo o arquivo `App.jsx`

Vá ao arquivo `App.jsx` que foi criado automaticamente para nós. Este arquivo é a raiz do nosso site e é onde vamos utilizar os nossos componentes.

O **conteúdo que veio pronto** é o seguinte:

```jsx
import './App.css'

export default function App() {
  return (
    <main>
      React ⚛️ + Vite ⚡ + Replit 🌀
    </main>
  )
}
```

Perceba como este código se parece muito com o código do arquivo `Card.jsx`: temos o `export default`, uma `funcion` Javascript retornando um código HTML e o próprio HTML junto com o Javascript.

Agora, vamos apagar a linha 6 para remover o conteúdo que foi gerado de exemplo.

```jsx
import './App.css'

export default function App() {
  return (
    <main>
    </main>
  )
}
```

Agora temos um site limpo e estamos prontos para adicionar o componente `Card`. Para isso, duas alterações são necessárias no `App.jsx`:
1. **Importar** o componente Card
2. **Utilizar** o componente Card

No código abaixo estamos aplicando estas 2 alterações. Veja nos comentários do código onde cada alteração é feita:

```jsx
import './App.css'
import Card from './Card' // Passo 1. Importando o componente Card

export default function App() {
  // Passo 2. Adicione <Card></Card> dentro da tag main abaixo:
  return (
    <main>
      <Card></Card>      
    </main>
  )
}
```

Na alteração 1 acima, temos outra novidade: o uso da palavra `import`. Não vamos entrar em detalhes agora, mas tenha em mente que o `import` neste caso funciona junto com o `export default` que utilizamos lá dentro do componente Card. Vamos explorar melhor esta funcionalidade nas próximas aulas.

Antes de passar para o passo seguinte, vamos adicionar o estilo do Card. Vá no arquivo `App.css` e coloque o seguinte código:

```css
div {
  text-align: center;
  vertical-align: center;
  line-height: 80px;
  border: 1px solid orange;
  margin-bottom: 8px;
}
```

Rode o projeto. O que aconteceu?

## Passo 4 - Explorando o uso do Componente `Card`

Pronto! Agora nosso site está exibindo corretamente o `Card` que criamos no arquivo `Card.jsx` 🎊. Perceba que o componente `Card` é utilizado como se fosse uma tag HTML no React, o que facilita muito o desenvolvimento de sites.

Agora, faça um teste. O que acontece se adicionarmos mais componentes `Card` no código? Tente executar o seu projeto com o seguinte conteúdo no arquivo `App.jsx`:

```
import './App.css'
import Card from './Card'

export default function App() {
  return (
    <main>
      <Card></Card>      
      <Card></Card>      
      <Card></Card>      
    </main>
  )
}
```

Qual o resultado do código acima?

## Próximos passos

Você chegou ao final da primeira Aula do Intensivo React 2023! Recomendamos que você assista os [2 vídeos listados nos materiais complementares dessa aula](./README.md#material-complementar). 
