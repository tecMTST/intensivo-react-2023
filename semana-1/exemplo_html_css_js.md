# Aula 01 - JS+HTML+CSS puros
Nesta aula iremos criar uma tela com alguns elementos que já estamos familiares em JS+HTML+CSS puros para depois entendermos como executá-los utilizando a biblioteca  React.js.

## Passo 01 - Iniciando
A primeira coisa  sse fazer é criar osa tríade do desenvolvimento web, ou seja:
 - HTML - index.html - O esqueleto de uma página web;
 - CSS - style.css - O estilo da página;
 - JS(JavaScript) - script.js - Responsável pela interação da página;

Inicialmente os arquivos devem se parecer como o seguinte:

**index.html:**
```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>replit</title>
    <link href="style.css" rel="stylesheet" type="text/css" />
</head>

<body>
    <p>Olá mundo!<p>
</body>
<script src="script.js"></script>
</html>
```
**style.css:**
```css
html {
  height: 100%;
  width: 100%;
}

.estilo-card {
  text-align: center;
  vertical-align: center;
  line-height: 80px;
  border: 3px solid orange;
  margin-top: 8px;
} 
```

**script.js:**
```js
console.log("...texto teste do consolog...")
```

---
## Passo 02 - Adicionando elementos na tela
Vamos manter as coisas simples apenas para nos familiarizar, vamos apenas colocar um título para a tela (utilizando a tag `<h1>`),  algum texto (tag `<p>`) e montar os cards.
**index.html:**
```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>replit</title>
    <link href="style.css" rel="stylesheet" type="text/css" />
</head>

<body>
    <h1>Cards:</h1>
    <p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc ac lobortis neque. Aliquam ultricies malesuada tortor, quis congue eros hendrerit.
    </p>
    <div class="estilo-card">
        <p>
            Este é o card
        </p>
</body>
<script src="script.js"></script>
</html>
```
Repare aqui que aplicamos já um estilo à `<div>` do card para que ele realmente se pareça com um card (vide estilo no "style.css").

Pronto, terminamos nossa tela só com HTML+CSS+JS (porém só usando HTML e CSS pois não adicionamos nenhuma interação à tela.)

---
## Próximos passos

Agora vamos entender como o mesmo site pode ser feito em React. [Acesse o próximo passo aqui](./exemplo_react.md).
