# Criando um componente
Vamos criar um componente e inseri-lo no DOM agora que entendemos um pouco melhor como os elementos são renderizados na página e como funciona a estrutura de um projeto utilizando React.
## Codando o componente propriamente dito
Para inciar criando um novo componente vamos utilizar um tempalte de React pronto que está no [Repl.it](https://replit.com/@replit/React-Javascript?v=1).<br>
Dentro da pasta `src` crie uma outra pasta para guardarmos o código dos componentes chamada  `components` e dentro dela vamos adicionar dois arquivos, o `Banner.jsx` e o `Banner.css`.
<br>

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

Nada vai acontecer, isso porque ainda nao inserimos o nosso componente recém criado para ser exibido no DOM.<br>

## Inserindo o componente no DOM

Para fazer isso vamos ter que inserir nosso componente na porta de entrada para os componentes React, o `App.jsx`.<br>


Em `./App.jsx`:
```jsx
import './App.css'
import Banner from './components/Banner'
export default function App() {
  return (
    <main>
      <Banner></Banner>
    </main>
  )
}
```
Tudo pronto! basta rodar o projeto agora