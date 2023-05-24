# Rascunho

## Planejamento aula 4

1. Olhando para o site e vendo o que vamos fazer
> - seção sobre e seção 'contribua com o núcleo'
> - identificar semelhanças entre eles
> - identificar diferenças entre eles

2. Fazendo o componente da seção sobre
> - nome descritivo
> - quais props podemos usar?
> - button, a, href e target
> > - diferença do mouse no hover
> - aplicar css
> > - destaque para o fit-content

visão final do componente:

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

visão final do css para esse componente:

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

3. Fazendo a seção 'Contribua com o Núcleo'

js final:

```js
import './SecaoContribua.css'

export default function SecaoContribua(props) {
  return (
    <div className='secao'>
      <h2>{(props.titulo).toUpperCase()}</h2>
      <div className='secaoConteudo'>
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

css final:

```css
.secao {
  background-color: #db4682;
  padding: 40px 200px;
  color: white;
  height: fit-content;
}

.secaoConteudo{
  font-size: 40px;
}

.secao img {
  width: 350px
}
```

4. Fazendo um componente para o botão
> - assunto novo: props.children
> > - se der tempo, aborar alguns exemplos de como podemos dar console.log nessa props e explorar esse children

js final:

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
css final:

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

css da seção Sobre agora com o componente Botao:

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
```

## Referências

- 
