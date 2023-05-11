# Criando um componente
Vamos exercitar a criação de um componente novo, dessa vez iniciando já com o Site do Núcleo de Tecnologia do MTST. Durante este processo como funciona a estrutura de um projeto utilizando React.

## Codando o componente propriamente dito
Para inciar criando um novo componente vamos utilizar um tempalte de React pronto que está no [Repl.it](https://replit.com/@replit/React-Javascript?v=1).<br>
Dentro da pasta `src` crie uma outra pasta para guardarmos o código dos componentes chamada  `componentes` e dentro dela vamos adicionar dois arquivos, o `BannerInicio.jsx` e o `BannerInicio.css`.

Em `./src/componentes/BannerInicio.jsx`:
```jsx
import './BannerInicio.css'

export default function BannerInicio() {

  return (
    <div id="container-banner-inicio">
      <div className="container-conteudo">
        <img src="https://nucleodetecnologia.com.br/assets/img/novo-logo-tecnologia.svg"/>
      </div>
    </div>
  )
}
```

Em `./src/componentes/BannerInicio.css`:

```css
#container-banner-inicio {
  background-color: #FFF5E6;
  text-align: center;
  padding: 48px 0;
  background-image: url("https://nucleodetecnologia.com.br/assets/img/capa-site.jpg");
  background-size: contain;
  background-position-y: center;
  background-position-x: center;
  background-repeat: no-repeat;	
}

#container-banner-inicio img {
  width: 320px;
}
```

Agora tente rodar o projeto...<br>

Nada vai acontecer, isso porque ainda não inserimos o nosso componente recém criado para ser exibido no site.<br>

## Inserindo o componente novo na tela

Para fazer isso vamos ter que inserir nosso componente na porta de entrada para os componentes React, o `App.jsx`.<br>


Em `./App.jsx`:
```jsx
import './App.css'
import BannerInicio from './componentes/BannerInicio'
export default function App() {
  return (
    <main>
      <BannerInicio></BannerInicio>
    </main>
  )
}
```

Tudo pronto! basta rodar o projeto agora para vermos nosso mais novo componente.
