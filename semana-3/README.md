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

```react
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

```react
export default function DigaBomDia(props) {
  return (
    <h2>
      Bom dia, {props.nome}!
    </h2>
  )
}
```

E, agora no `App` chamar dessa forma:

```react
<DigaBomDia nome='Pedro'/>
```

Na tela agora vai mostrar "Bom dia, Pedro!". E se você fizer assim:

```react
<DigaBomDia nome='Pedro'/>
<DigaBomDia nome='João'/>
<DigaBomDia nome='Maria'/>
```

Na tela vai aparecer o 'Bom dia' para essas pessoas. Você poderia até fazer seu site perguntar o nome da pessoa antes de dar bom dia, por exemplo.

Essa ferramenta props é muito útil. Digamos que no nosso site queremos ter um componente que é sempre igual, e que muda somente algumas partes do seu interior. Por exemplo, a parte 'iniciativas' do site do núcleo:

### Usando props na seção 'iniciativas' do site do núcleo

# TODO


