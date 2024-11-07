# CSS Variables (Variáveis CSS)

## Introdução

CSS Variables, também conhecidas como Custom Properties, são entidades definidas pelos desenvolvedores que contêm valores específicos para serem reutilizados em todo o documento CSS. Elas permitem criar códigos mais manuteníveis, consistentes e flexíveis.

## Sintaxe Básica

### Declaração de Variáveis

As variáveis CSS são declaradas usando dois traços (--) seguidos pelo nome da variável:

```css
:root {
  --nome-da-variavel: valor;
}
```

### Uso de Variáveis

Para utilizar uma variável, usamos a função `var()`:

```css
elemento {
  propriedade: var(--nome-da-variavel);
}
```

## Vantagens

1. **Manutenibilidade**
   - Alterações centralizadas
   - Redução de redundância
   - Facilidade de atualização

2. **Consistência**
   - Padronização de valores
   - Prevenção de erros
   - Design system simplificado

3. **Flexibilidade**
   - Criação de temas
   - Adaptação responsiva
   - Manipulação via JavaScript

## Exemplo Prático

Aqui está um exemplo completo demonstrando o uso de CSS Variables:

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS Variables - Exemplo Prático</title>
    <style>
        /* Definindo variáveis globais no root */
        :root {
            /* Cores principais */
            --cor-primaria: #007bff;
            --cor-secundaria: #6c757d;
            --cor-sucesso: #28a745;
            --cor-perigo: #dc3545;
            --cor-alerta: #ffc107;
            --cor-info: #17a2b8;
            
            /* Variáveis de layout */
            --espacamento-padrao: 20px;
            --fonte-principal: 'Arial', sans-serif;
            --sombra-padrao: 0 2px 5px rgba(0,0,0,0.2);
        }

        body {
            font-family: var(--fonte-principal);
            margin: 0;
            padding: var(--espacamento-padrao);
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
        }

        .card {
            background: white;
            padding: var(--espacamento-padrao);
            margin-bottom: var(--espacamento-padrao);
            border-radius: 8px;
            box-shadow: var(--sombra-padrao);
        }

        /* Botões com diferentes cores */
        .botao-primario {
            background-color: var(--cor-primaria);
            color: white;
            padding: calc(var(--espacamento-padrao) / 2);
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        .botao-secundario {
            background-color: var(--cor-secundaria);
            color: white;
            padding: calc(var(--espacamento-padrao) / 2);
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        .botao-sucesso {
            background-color: var(--cor-sucesso);
            color: white;
            padding: calc(var(--espacamento-padrao) / 2);
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        .botao-perigo {
            background-color: var(--cor-perigo);
            color: white;
            padding: calc(var(--espacamento-padrao) / 2);
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        /* Exemplo de tema escuro */
        .tema-escuro {
            --cor-primaria: #4a90e2;
            --cor-secundaria: #868e96;
            --cor-sucesso: #3db557;
            --cor-perigo: #e74c3c;
            background-color: #1a1a1a;
            color: white;
        }

        /* Responsividade */
        @media (max-width: 600px) {
            :root {
                --espacamento-padrao: 10px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="card">
            <h1>Demonstração de CSS Variables</h1>
            <p>Este é um exemplo de texto usando variáveis CSS.</p>
            <button class="botao-primario">Botão Primário</button>
            <button class="botao-secundario">Botão Secundário</button>
            <button class="botao-sucesso">Botão Sucesso</button>
            <button class="botao-perigo">Botão Perigo</button>
        </div>
    </div>
</body>
</html>
```

## Boas Práticas

1. **Nomenclatura**
   - Use nomes descritivos
   - Siga um padrão consistente
   - Prefira kebab-case para nomes de variáveis

2. **Organização**
   - Declare variáveis globais no `:root`
   - Agrupe variáveis relacionadas
   - Comente seções importantes

3. **Escopo**
   - Use escopo local quando necessário
   - Evite sobrescrita desnecessária
   - Mantenha a hierarquia lógica

## Casos de Uso Comuns

1. **Temas**
   - Light/Dark mode
   - Variações de marca
   - Personalização por usuário

2. **Responsividade**
   - Adaptação de tamanhos
   - Alteração de espaçamentos
   - Modificação de layouts

3. **Componentes**
   - Variações de estado
   - Modificadores
   - Versões alternativas

## Suporte dos Navegadores

CSS Variables tem excelente suporte nos navegadores modernos:
- Chrome 49+
- Firefox 31+
- Safari 9.1+
- Edge 15+

## Conclusão

CSS Variables são uma ferramenta poderosa para criar códigos CSS mais manuteníveis e flexíveis. Elas facilitam a criação de temas, a adaptação responsiva e a manutenção de design systems consistentes.
