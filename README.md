# Guia de CSS

## Índice
- [Seletores](#seletores)
- [Box Model](#box-model)
- [Tipografia](#tipografia)
- [Cores e Fundos](#cores-e-fundos)
- [Layout](#layout)
- [Flexbox](#flexbox)
- [Grid](#grid)
- [Transições e Animações](#transições-e-animações)
- [Media Queries](#media-queries)
- [Incorporação CSS](#incorporação-css)

## Seletores

### Seletores Básicos
```css
/* Elemento - seleciona todos os parágrafos */
p {
    color: blue;
}

/* Classe - seleciona elementos com classe 'destaque' */
.destaque {
    background-color: yellow;
}

/* ID - seleciona elemento com ID 'cabecalho' */
#cabecalho {
    position: fixed;
}

/* Atributo - seleciona todos os inputs do tipo 'text' */
[type="text"] {
    border: 1px solid gray;
}

/* Múltiplos seletores */
h1, h2, h3 {
    font-family: Arial;
}
```

### Combinadores
```css
/* Descendente - seleciona todos os parágrafos dentro de div */
div p {
    margin: 10px;
}

/* Filho direto - seleciona apenas ul que são filhos diretos de nav */
nav > ul {
    list-style: none;
}

/* Irmão adjacente - seleciona o primeiro p após um h2 */
h2 + p {
    font-weight: bold;
}

/* Irmãos gerais - seleciona todos os p que são irmãos de h2 */
h2 ~ p {
    color: gray;
}
```

## Box Model

### Dimensões
```css
width: 100px;           /* Largura */
height: 100px;          /* Altura */
max-width: 100%;        /* Largura máxima */
min-width: 50px;        /* Largura mínima */
box-sizing: border-box; /* Inclui padding e border na dimensão total */
```

### Margens e Padding
```css
margin: 10px;                    /* Margem em todos os lados */
margin: 10px 20px;              /* Margem vertical | horizontal */
margin: 10px 20px 15px 25px;    /* Topo | Direita | Baixo | Esquerda */
padding: 10px;                  /* Preenchimento interno */
```

### Bordas
```css
border: 1px solid black;   /* Largura | Estilo | Cor */
border-radius: 5px;        /* Bordas arredondadas */
border-style: solid;       /* Estilo da borda */
border-width: 1px;         /* Largura da borda */
border-color: black;       /* Cor da borda */
```

## Tipografia

### Fonte
```css
font-family: Arial, sans-serif;  /* Família da fonte */
font-size: 16px;                 /* Tamanho da fonte */
font-weight: bold;               /* Peso da fonte */
font-style: italic;              /* Estilo da fonte */
line-height: 1.5;                /* Altura da linha */
text-align: center;              /* Alinhamento do texto */
text-decoration: underline;      /* Decoração do texto */
```

### Espaçamento
```css
letter-spacing: 1px;    /* Espaçamento entre letras */
word-spacing: 2px;      /* Espaçamento entre palavras */
text-indent: 20px;      /* Recuo da primeira linha */
```

## Cores e Fundos

### Cores
```css
color: #ff0000;                /* Cor do texto (hexadecimal) */
color: rgb(255, 0, 0);        /* Cor do texto (RGB) */
color: rgba(255, 0, 0, 0.5);  /* Cor do texto com transparência */
opacity: 0.5;                 /* Transparência do elemento */
```

### Fundos
```css
background-color: #f0f0f0;           /* Cor de fundo */
background-image: url('imagem.jpg'); /* Imagem de fundo */
background-repeat: no-repeat;        /* Repetição do fundo */
background-position: center;         /* Posição do fundo */
background-size: cover;              /* Tamanho do fundo */
```

## Layout

### Display
```css
display: block;           /* Elemento em bloco */
display: inline;         /* Elemento em linha */
display: inline-block;   /* Bloco em linha */
display: none;           /* Oculta o elemento */
```

### Posicionamento
```css
position: relative;     /* Posicionamento relativo */
position: absolute;     /* Posicionamento absoluto */
position: fixed;        /* Posicionamento fixo */
top: 0;                /* Distância do topo */
left: 0;               /* Distância da esquerda */
z-index: 1;            /* Ordem de empilhamento */
```

## Flexbox

### Container Flex
```css
display: flex;              /* Define container flex */
flex-direction: row;        /* Direção dos itens */
justify-content: center;    /* Alinhamento horizontal */
align-items: center;        /* Alinhamento vertical */
flex-wrap: wrap;           /* Quebra de linha */
gap: 10px;                 /* Espaçamento entre itens */
```

### Itens Flex
```css
flex: 1;                   /* Crescimento proporcional */
flex-grow: 1;             /* Fator de crescimento */
flex-shrink: 1;           /* Fator de redução */
flex-basis: auto;         /* Tamanho base */
align-self: center;       /* Alinhamento individual */
```

## Grid

### Container Grid
```css
display: grid;                           /* Define container grid */
grid-template-columns: 1fr 1fr 1fr;      /* Colunas do grid */
grid-template-rows: 100px auto;          /* Linhas do grid */
grid-gap: 10px;                         /* Espaçamento entre células */
grid-template-areas: "header header"     /* Áreas nomeadas */
                     "main sidebar"
                     "footer footer";
```

### Itens Grid
```css
grid-column: 1 / 3;        /* Posição nas colunas */
grid-row: 1 / 2;          /* Posição nas linhas */
grid-area: header;        /* Área nomeada */
```

## Transições e Animações

### Transições
```css
transition: all 0.3s ease;              /* Propriedade | Duração | Timing */
transition-property: transform;          /* Propriedade a animar */
transition-duration: 0.3s;              /* Duração da transição */
transition-timing-function: ease;        /* Função de temporização */
transition-delay: 0.1s;                 /* Atraso antes da transição */
```

### Animações
```css
@keyframes slide {
    0% { transform: translateX(0); }
    100% { transform: translateX(100px); }
}

animation: slide 2s ease infinite;      /* Nome | Duração | Timing | Iterações */
animation-name: slide;                  /* Nome da animação */
animation-duration: 2s;                 /* Duração da animação */
animation-timing-function: ease;        /* Função de temporização */
animation-iteration-count: infinite;    /* Número de repetições */
```

## Media Queries

### Responsividade
```css
@media screen and (max-width: 768px) {
    /* Regras para telas até 768px */
}

@media screen and (min-width: 769px) and (max-width: 1024px) {
    /* Regras para telas entre 769px e 1024px */
}

@media print {
    /* Regras para impressão */
}
```

### Orientação
```css
@media (orientation: landscape) {
    /* Regras para orientação paisagem */
}

@media (orientation: portrait) {
    /* Regras para orientação retrato */
}
```

## Incorporação CSS

### 1. CSS Inline
```html
<!-- Não recomendado para uso frequente -->
<p style="color: blue; font-size: 16px;">Texto com estilo inline</p>
```
Prós:
- Maior especificidade
- Útil para estilos únicos e específicos

Contras:
- Difícil manutenção
- Código não reutilizável
- Mistura conteúdo com apresentação

### 2. CSS Interno (Internal Stylesheet)
```html
<head>
    <style>
        p {
            color: blue;
            font-size: 16px;
        }
    </style>
</head>
```
Prós:
- Não precisa carregar arquivo externo
- Útil para páginas únicas

Contras:
- Aumenta o tamanho do HTML
- Estilos não são compartilhados entre páginas
- Dificulta a manutenção em sites grandes

### 3. CSS Externo (External Stylesheet)
```html
<head>
    <!-- Método preferido -->
    <link rel="stylesheet" href="styles.css">
    
    <!-- Alternativa usando @import (não recomendado) -->
    <style>
        @import url("styles.css");
    </style>
</head>
```
Prós:
- Melhor manutenibilidade
- Arquivos podem ser cacheados
- Separação clara entre conteúdo e apresentação
- Reutilização de código

Contras:
- Requisição adicional ao servidor

### Melhores Práticas de Incorporação CSS

1. **Priorize CSS Externo**
   - Use arquivos .css externos como método principal
   - Organize os arquivos por funcionalidade ou componente

2. **Ordem de Carregamento**
   ```html
   <head>
       <!-- CSS Reset/Normalize primeiro -->
       <link rel="stylesheet" href="normalize.css">
       
       <!-- Frameworks e bibliotecas depois -->
       <link rel="stylesheet" href="framework.css">
       
       <!-- Seus estilos por último -->
       <link rel="stylesheet" href="styles.css">
   </head>
   ```

3. **Otimização**
   - Minifique arquivos CSS em produção
   - Use media queries no link para carregamento condicional:
   ```html
   <link rel="stylesheet" href="print.css" media="print">
   <link rel="stylesheet" href="mobile.css" media="screen and (max-width: 768px)">
   ```

4. **Preload para Arquivos Críticos**
   ```html
   <link rel="preload" href="critical.css" as="style">
   ```

5. **Evite @import em Produção**
   - Causa carregamento em série
   - Impacta negativamente a performance

6. **Comentários e Organização**
   ```css
   /* ==========================================================================
      Seção Principal
      ========================================================================== */
   
   /* Subsistema
      ========================================================================== */
   ```

7. **Convenções de Nomenclatura**
   - Use metodologias como BEM, SMACSS ou OOCSS
   - Mantenha consistência no projeto
   ```css
   /* Exemplo usando BEM */
   .bloco {}
   .bloco__elemento {}
   .bloco--modificador {}
   ```
