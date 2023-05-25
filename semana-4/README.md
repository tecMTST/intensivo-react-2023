# Aula 4

## Olhando para o site e planejando o que vamos fazer hoje

Vamos dar uma olhada na seção "Sobre" e na seção "Contribua com o Núcleo". Vamos identificar as semelhanças e diferenças entre essas seções. Analise os elementos visuais, o posicionamento do conteúdo e o comportamento interativo dos elementos.

Identificar semelhanças:
- Ambas as seções podem ter um título ou cabeçalho que as identifica.
- Ambas podem conter texto descritivo que explica o propósito da seção.
- Pode haver um botão ou link que leva a outra página ou seção do site.

Identificar diferenças:
- A seção "Contribua com o Núcleo" vai ter uma imagem
- A seção "Sobre" vai ter um botão.

Agora que temos uma compreensão básica do que queremos criar, vamos começar a fazer o componente da seção "Sobre".

## Fazendo o componente da seção "Sobre"

Para criar o componente da seção "Sobre", precisamos definir um nome descritivo para ele. Vamos chamá-lo de `SecaoSobre`.

Quais props podemos usar?
Aqui estão algumas props que podemos usar para tornar nosso componente mais flexível e reutilizável:
- `titulo`: uma prop que recebe o título da seção.
- `textoSimples`: uma prop que recebe o texto descritivo simples da seção.
- `textoDestaque`: uma prop que recebe o texto descritivo de destaque da seção.

Como o componente vai ficar:

```js
import './SecaoSobre.css'

export default function SecaoSobre(props) {
  return (
    <div className='secaoSobre'>
      <h2>{(props.titulo).toUpperCase()}</h2>
      <div className='secaoSobreConteudo'>
        <p>{props.textoSimples}</p>
        <p><b>{props.textoDestaque}</b></p>
      </div>
    </div>
  )
}
```

### Button, a, href e target:

Dentro do componente `SecaoSobre`, podemos usar um elemento de botão (`<button>`) ou um elemento de link (`<a>`) para o botão da seção. A escolha depende do comportamento esperado. 
- Se quisermos que o botão execute uma ação no próprio site, podemos usar o elemento de botão.
- Se quisermos redirecionar para outra página ou site, podemos usar o elemento de link.

Ao usar o elemento `<a>` com o atributo `href` e `target="_blank"`, o link será aberto em uma nova aba ou janela do navegador.

### Diferença do mouse no hover:

Uma diferença notável ao interagir com os elementos do site pode ser a alteração do estilo quando o mouse está em cima deles. Por exemplo, o ícone do mouse mude de um para outro, no <a> ele vira uma mãozinha, no <button> não.

Adicionando o botão com a tag <a> no componente:

```js
import './SecaoSobre.css'

export default function SecaoSobre(props) {
  return (
    <div className='secaoSobre'>
      <h2>{(props.titulo).toUpperCase()}</h2>
      <div className='secaoSobreConteudo'>
        <p>{props.textoSimples}</p>
        <p><b>{props.textoDestaque}</b></p>
      </div>
      <button>
        <a
          href='https://www.instagram.com/tecnologia.mtst/'
          target='_blank'
        >
          Siga nosso Instagram
        </a>
      </button>
    </div>
  )
}
```

Aplicar CSS:

```css
.secaoSobre {
  background-color: #db4682;
  padding: 40px 200px;
  color: white;
  height: fit-content;
}

.secaoSobre h2{
  font-size:60px;
  margin: 0;
}

.secaoSobreConteudo{
  font-size: 40px;
  color: white;
}

.secaoSobre a {
  background-color: transparent;
  border-color: white;
  color: white;
  border-radius: 5px;
  border: 1px solid;
  font-size: large;
  padding: 20px;
  font-weight: bold;
  text-decoration: none;
}

.secaoSobre a:hover {
  color: #212529;
  background-color: #f8f9fa;
  border-color: #f8f9fa;
}

.secaoSobre button {
  border: none;
  background-color: transparent;
  margin-bottom: 20px;
}
```

## Fazendo a seção 'Contribua com o Núcleo'

Agora vamos criar a seção "Contribua com o Núcleo", que terá uma estrutura semelhante à seção "Sobre". No entanto, há algumas diferenças importantes:

Props que serão criadas:
- `titulo`: recebe o título da seção.
- `textoSimples1`: recebe um texto simples.
- `textoDestaque1`: recebe um texto em destaque.
- `textoDestaque2`: recebe outro texto em destaque.
- `textoSimples2`: recebe um segundo texto simples.
- Em vez de um botão, a seção "Contribua com o Núcleo" terá uma imagem.

Aqui está o código JavaScript final para o componente `SecaoContribua`:

```js
import './SecaoContribua.css'

export default function SecaoContribua(props) {
  return (
    <div className='secaoContribua'>
      <h2>{(props.titulo).toUpperCase()}</h2>
      <div className='secaoContribuaConteudo'>
        <p>
          {props.textoSimples1}
        </p>
        <p>
          <b>
            {props.textoDestaque1}
          </b>
        </p>
        <p>
          <b>
            {props.textoDestaque2}
          </b>
        </p>
        <p>
          {props.textoSimples2}
        </p>
      </div>
      <img
        src='https://nucleodetecnologia.com.br/assets/img/pix-mtst.jpg'
      />
    </div>
  )
}
```

Aqui está o código CSS final para estilizar o componente `SecaoContribua`:

```css
.secaoContribua {
  background-color: #db4682;
  padding: 40px 200px;
  color: white;
  height: fit-content;
}

.secaoContribua h2 {
  font-size: 60px;
  margin: 0;
}

.secaoContribuaConteudo{
  font-size: 40px;
}

.secaoContribua img {
  width: 350px;
}
```

Neste exemplo, aplicamos estilos ao componente `SecaoContribua` usando classes CSS. Definimos o fundo, o espaçamento interno, a cor do texto e a altura do componente. 

---

## Fazendo um componente para o botão

Agora vamos criar um componente para o botão, chamado `Botao`. Antes disso, vamos abordar o conceito de `props.children` e explorar seus usos mais comuns.

`props.children` é uma prop especial no React que permite passar elementos filhos para um componente. Esses elementos podem ser outros componentes, texto ou até mesmo estruturas mais complexas. É uma forma flexível de compor componentes e torná-los mais reutilizáveis.

> Vamos explorar as props usando `console.log()`!

Aqui está o código JavaScript final para o componente `Botao`:

```js
import './Botao.css'

export default function Botao(props) {
  return (
    <button className='botaoComponente'>
      <a
        href={props.levaPraOnde}
        target="_blank"
      >
        {props.children}
      </a>
    </button>
  )
}
```

Agora que temos nosso componente `Botao`, podemos utilizá-lo em outros componentes, passando o conteúdo desejado como `props.children`. Por exemplo, podemos usar o componente `Botao` dentro da seção "Sobre" para substituir o botão existente:

```jsx
<Botao levaPraOnde="https://www.exemplo.com">
  Saiba mais
</Botao>
```

O conteúdo "Saiba mais" será renderizado dentro do componente `Botao` como seu `props.children`.

Aqui está o código CSS final para estilizar o componente `Botao`:

```css
.botaoComponente a {
  background-color: transparent;
  border-color: white;
  color: white;
  border-radius: 5px;
  border: 1px solid;
  font-size: large;
  padding: 20px;
  font-weight: bold;
  text-decoration: none;
}

.botaoComponente a:hover {
  color: #212529;
  background-color: #f8f9fa;
  border-color: #f8f9fa;
}

.botaoComponente {
  border: none;
  background-color: transparent;
  margin: 0 0 30px 0;
}
```

Aqui está o código CSS atualizado para a seção "Sobre" utilizando o componente `Botao`:

```css
.secaoSobre {
  background-color: #db4682;
  padding: 40px 200px;
  color: white;
  height: fit-content;
}

.secaoSobre h2 {
  font-size: 60px;
  margin: 0;
}

.secaoSobreConteudo {
  font-size: 40px;
  color: white;
}

.secaoSobre a {
  background-color: transparent;
  border-color: white;
  color: white;
  border-radius: 5px;
  border: 1px solid;
  font-size: large;
  padding: 20px;
  font-weight: bold;
  text-decoration: none;
}
```

Continue praticando e explorando o React!

## Referências

- React:
  - [Documentação oficial do React](https://reactjs.org/docs/getting-started.html)
  - [Tutorial do React no MDN](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_getting_started)

- Props:
  - [Componentes e Props no React](https://pt-br.reactjs.org/docs/components-and-props.html)
  - [Understanding React `children` Utilities](https://www.freecodecamp.org/news/react-children-api-explained/)
  
- CSS:
  - [Guia de CSS do MDN](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Guide)
  - [Box model no CSS](https://developer.mozilla.org/pt-BR/docs/Web/CSS/box_model)
  - [Seletores CSS](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Referencia_de_seletores)
