# Aula 4

- [Aula 4](#aula-4)
  - [Objetivos](#objetivos)
- [Funções no JavaScript](#funções-no-javascript)
- [Navegando Arquivos](#navegando-arquivos)
- [JavaScript com React](#javascript-com-react)
- [Props do React](#props-do-react)

Conforme chegamos ao meio de nosso intensivão, é bom relembrar alguns tópicos chaves e reforçar seus usos.

### Objetivos

Nesta aula, revisitaremos os seguintes tópicos:

- retornos de parâmetros e funções
- `import`/`export`: navegação em arquivos
- código JavaScript dentro do componente react
- uso de `props` no React

Para reforçar essas idéias, estaremos fazendo alguns exercícios juntos.

# Funções no JavaScript

# Navegando Arquivos

Conforme adicionamos mais componentes no nosso site, a estrutura de nossos arquivos vai ficando cada vez mais complexa.
No momento em que finalizamos a [Aula 3](../semana-3/README.md), nossos arquivos estavam organizados dessa forma:

```
.
│   App.css
│   App.jsx
│   index.jsx
│
└───componentes
    │   BannerInicio.css
    │   BannerInicio.jsx
    │
    ├───botao
    │       Botao.css
    │       Botao.jsx
    │
    ├───iniciativas
    │       CardIniciativa.css
    │       CardIniciativa.jsx
    │       SecaoIniciativas.css
    │       SecaoIniciativas.jsx
    │
    └───secaoSobre
            SecaoContribua.css
            SecaoContribua.jsx
            SecaoSobre.css
            SecaoSobre.jsx
            SecaoSobreComBotao.jsx
            SecaoSobreComChildren.jsx
```

Temos a pasta `componentes`, e dentro dela criamos 3 outras pastas: `botao`, `iniciativas` e `secaoSobre`.

Quando queremos falar pro React usar um componente no `App.jsx`, nós temos que explicar onde exatamente ele tem que ir procurar nosso componente.

# JavaScript com React

# Props do React
