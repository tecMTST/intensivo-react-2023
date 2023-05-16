# Aula 3
Olá, nessa aula vamos aprender sobre como os componentes se comunicam usando props. [Pesquise!](https://www.google.com/search?q=o+que+s%C3%A3o+props+em+react&sxsrf=APwXEdexYMeCedue1yKie2G2FJEADJ6Pig%3A1684070664733&ei=COFgZMW1LIHc1sQP-JiwsA0&ved=0ahUKEwjF2f2N9PT-AhUBrpUCHXgMDNYQ4dUDCBA&uact=5&oq=o+que+s%C3%A3o+props+em+react&gs_lcp=Cgxnd3Mtd2l6LXNlcnAQAzIFCAAQgAQyBQgAEIAEMgYIABAWEB46CggAEEcQ1gQQsAM6CggAEIoFELADEEM6BAgjECc6BwgjEIoFECc6BwgAEIoFEEM6EQguEIAEELEDEIMBEMcBENEDOggIABCABBCxAzoLCAAQgAQQsQMQgwE6BwgAEIAEEAo6CAgAEIoFELEDOgsIABAWEB4Q8QQQCjoICAAQFhAeEAo6BwgAEA0QgAQ6CQgAEA0QgAQQCjoICAAQHhANEA86CAgAEBYQHhAPSgQIQRgAUO0iWIRbYL1daANwAXgAgAGxAYgBshySAQQwLjI3mAEAoAEByAEKwAEB&sclient=gws-wiz-serp)

## Props
Pesquisou? Caso não, aiaiai, que cosa fea. Props são a abreviação da palavra inglesa 'properties' ou propriedades. E você já mexeu com uma coisa parecida!

Quando você estava aprendendo sobre javascript você mexeu com funções e argumentos de função. Vamos relembrar:

### Relembrando sobre argumentos de função
Digamos que eu tenho uma função javascript definida assim:

```js
function digaBomDia(nome) {
    console.log(`Bom dia, ${nome}!`)
}
```

E eu chamo essa função assim:

```js
digaBomDia('Pedro')
=> 'Bom dia, Pedro!'
```

Bom nesse caso a variável `nome` é o argumento que passamos para a função `digaBomDia`. E, nesse nosso exemplo essa variável espera uma string que representa o nome de uma pessoa. Eu poderia chamar a mesma função passando outros nomes:

```js
digaBomDia('João')
=> 'Bom dia, João!'

digaBomDia('Maria')
=> 'Bom dia, Maria!'
```

Ou seja, argumentos de função nos permitem ter flexibilidade no resultado da função que definimos.

Bem podemos fazer a mesma coisa com props em react. Sendo que nesse caso, props são os 'argumentos' que podemos passar para um componente react:

### Exemplo de props em react

Digamos que temos um componente assim:

```jsx
export default function DigaBomDia() {
  return (
    <h2>
      Bom dia!
    </h2>
  )
}
```

Se você chamar o componente no seu componente principal `App` (lembre de exportar/importar). Na tela vai dizer "Bom dia!"

Mas se queremos que o 'Bom dia' seja para uma pessoa como fizemos na função acima?

Podemos modificar o componente dessa forma:

```jsx
export default function DigaBomDia(props) {
  return (
    <h2>
      Bom dia, {props.nome}!
    </h2>
  )
}
```

E, agora no `App` chamar dessa forma:

```jsx
<DigaBomDia nome='Pedro'/>
```

Na tela agora vai mostrar "Bom dia, Pedro!". E se você fizer assim:

```jsx
<DigaBomDia nome='Pedro'/>
<DigaBomDia nome='João'/>
<DigaBomDia nome='Maria'/>
```

Na tela vai aparecer o 'Bom dia' para essas pessoas. Você poderia até fazer seu site perguntar o nome da pessoa antes de dar bom dia, por exemplo.

Essa ferramenta props é muito útil. Digamos que no nosso site queremos ter um componente que é sempre igual, e que muda somente algumas partes do seu interior. Por exemplo, a parte 'iniciativas' do site do núcleo:

### Usando props na seção 'iniciativas' do site do núcleo

A partir do projeto já com o [banner de inicio](https://github.com/tecMTST/intensivo-react-2023/blob/main/semana-2/criando_componente.md).

Ou, se você quiser, comece um replit-react do zero e delete o conteudo do arquivo `App.css`.

Crie uma pasta nova dentro da pasta componentes com o seguinte nome: `iniciativas`. E dentro dessa pasta crie dois arquivos: `SecaoIniciativas.jsx` e `SecaoIniciativas.css`.

Dentro do arquivo `SecaoIniciativas.jsx` coloque o seguinte conteúdo

```jsx
import './SecaoIniciativas.css'

export default function SecaoIniciativas() {
  return (
    <div>
      <h2>INICIATIVAS</h2>
    </div>
  )
}

```

E no arquivo `App.jsx` chame o novo componente após o componente `<BannerInicio></BannerInicio>` Ou simplesmente substitua o conteúdo auto gerado pela chamada desse novo componente. E ai? sabe fazer? O que ocorreu na tela depois disso?

Esse componente inicial vai armazenar outros componentes dentro dele que vamos chamar de `CardIniciativa`. Agora você vai começar a entender o dinamismo e o potencial de construção do react!

Crie dois novos arquivos na pasta `componentes/iniciativas`: `CardIniciativa.jsx` e `CardIniciativa.css`.

Se você observar o site do núcleo, você verá que cada Card ali tem uma imagem de fundo e um texto embaixo falando o nome da iniciativa. No site do núcleo também é possivel ver algumas interações quando passamos o mouse por cima do card e quando clicamos nele. Por enquanto não vamos fazer isso. Só criar os cards mesmo.

Pergunte-se. Como podemos escrever um só componente, que vai receber imagens e texto diferentes? E na tela veremos várias iniciativas?

A resposta é: usando props, e chamando o novo componente passando cada uma das iniciativas. Então vamos lá:

No componente `CardIniciativa.jsx` escreva o seguinte código:

```jsx
import './CardIniciativa.css'

export default function CardIniciativa(props) {
  return (
    <div className="container-card-modal">
      <img src={props.imagem} />
      <h4>{props.nome}</h4>
    </div>    
  )
}
```

Agora, no componente `SecaoIniciativas` vamos chamar esse componente `CardIniciativa` 3 vezes após o `h2`, passando conteúdos diferentes por props:

```jsx
<CardIniciativa
  nome="Curso de Programação"   
  imagem="https://nucleodetecnologia.com.br/assets/img/portfolio/programacao.png"
/>
<CardIniciativa
  nome="Contrate quem luta"   
  imagem="https://nucleodetecnologia.com.br/assets/img/portfolio/contrate.png"
/>
<CardIniciativa
  nome="App da Vitória"   
  imagem="https://nucleodetecnologia.com.br/assets/img/portfolio/app-vitoria.png"
/>
```

Perceba que no site já apareceram os conteúdos novos, porém estão desorganizados. Para organizá-los precisamos agrupar coisas semelhantes em divs.

Esses três cards por exemplo devem se comportar da mesma forma no que toca posição na tela. Vamos então colocá-los dentros dessas divs:

```jsx
<div className="container-conteudo">
  <h2>INICIATIVAS</h2>

  <div className="container-cards">
    ... <- aqui vem os cards :-)    
  </div>
</div>
```

Com as divs criadas com suas classes internas declaradas, podemos adicionar estilo no arquivo `SecaoIniciativas.css`:

```css
.container-cards {
  display: flex;
  justify-content: space-between;
}
```

Com essa alteração ja teremos os cards lado a lado, mas eles ainda estão grandes. No arquivo `CardIniciativa.css` coloque a seguintes regras:


```css
.container-card-modal {
  width: 100%;
  max-width: 400px;
  height: auto;
  margin-left: 24px;
  margin-right: 24px;

  cursor: pointer;
}

.container-card-modal img {
  border-radius: 8px;
  width: 100%;
  height: 100%;
}

```


Com essas alterações a gente já tem os card organizados. Se você observar o site do núcleo, verá que lá tem mais 3 cards. Você consegue adicioná-los?

Pode ser que quando você adicionar os outros 3, eles não fiquem numa linha separada. Para fazer isso, coloque esses outros três em uma outra div dessa forma:

```jsx
<div className="container-cards">
  <- os cards vem aqui :-D
</div>
```