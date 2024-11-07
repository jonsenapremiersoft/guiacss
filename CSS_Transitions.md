# CSS Transitions: Animações Suaves no CSS

## Introdução
As transições CSS permitem que mudanças nos valores das propriedades CSS ocorram de forma suave durante um período determinado, em vez de acontecerem instantaneamente. São ideais para melhorar a experiência do usuário e adicionar interatividade às interfaces.

## Propriedades Principais

### 1. transition-property
Define quais propriedades CSS serão animadas.

```css
.elemento {
    transition-property: all; /* Todas as propriedades */
    transition-property: background-color; /* Apenas background-color */
    transition-property: transform, opacity; /* Múltiplas propriedades */
}
```

### 2. transition-duration
Define a duração da transição em segundos (s) ou milissegundos (ms).

```css
.elemento {
    transition-duration: 0.3s; /* 300 milissegundos */
    transition-duration: 1s; /* 1 segundo */
}
```

### 3. transition-timing-function
Define como a transição progride ao longo do tempo.

```css
.elemento {
    transition-timing-function: ease; /* Padrão */
    transition-timing-function: linear; /* Velocidade constante */
    transition-timing-function: ease-in; /* Começa devagar */
    transition-timing-function: ease-out; /* Termina devagar */
    transition-timing-function: ease-in-out; /* Começa e termina devagar */
}
```

### 4. transition-delay
Define um atraso antes da transição começar.

```css
.elemento {
    transition-delay: 0.5s; /* Espera 500ms antes de iniciar */
}
```

## Shorthand
Você pode combinar todas as propriedades em uma única declaração:

```css
.elemento {
    /* propriedade duração timing-function delay */
    transition: all 0.3s ease-in-out 0s;
}
```

## Exemplos Práticos

### 1. Botão com Hover Suave
```css
.button {
    background-color: #3498db;
    padding: 10px 20px;
    color: white;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: #2980b9;
}
```

### 2. Card com Elevação
```css
.card {
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    transform: translateY(0);
    transition: all 0.3s ease;
}

.card:hover {
    box-shadow: 0 4px 8px rgba(0,0,0,0.2);
    transform: translateY(-5px);
}
```

### 3. Menu com Sublinhado
```css
.menu-item {
    position: relative;
    color: #333;
}

.menu-item::after {
    content: '';
    position: absolute;
    bottom: -2px;
    left: 0;
    width: 0;
    height: 2px;
    background-color: #3498db;
    transition: width 0.3s ease;
}

.menu-item:hover::after {
    width: 100%;
}
```

### 4. Ícone com Rotação
```css
.icon {
    transition: transform 0.3s ease;
}

.icon:hover {
    transform: rotate(90deg);
}
```

## Dicas Importantes

1. **Performance**: Priorize a animação de propriedades que afetam menos o layout:
   - transform
   - opacity
   - filter

2. **Duração**: 
   - Para interfaces responsivas: 200-300ms
   - Para efeitos mais elaborados: 500-800ms
   - Evite durações maiores que 1s

3. **Acessibilidade**: 
   - Use `prefers-reduced-motion` para respeitar as preferências do usuário:
```css
@media (prefers-reduced-motion: reduce) {
    * {
        transition: none !important;
    }
}
```

## Casos de Uso Comuns
- Hover em botões e links
- Menus expansíveis
- Mudanças de estado em formulários
- Feedback visual em interações
- Animações de carregamento
- Transições entre estados de componentes
