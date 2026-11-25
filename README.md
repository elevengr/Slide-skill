# slides-html

Uma skill para o Claude que cria apresentações em slides em um **único arquivo `.html`**, sobre qualquer tema, com visual autoral e animações, sem cara de template ou de IA.

Funciona 100% offline: só HTML, CSS e JavaScript puro, sem frameworks, sem CDN e sem imagens ou fontes externas.

## O que ela faz

- Gera slides a partir de um **PDF, documento, texto colado ou apenas um tema**
- **Pergunta o tamanho antes de gerar**: quantidade de slides (curta, média, longa ou número exato) e proporção (16:9, 4:3, quadrado ou vertical)
- Segue o roteiro do usuário, se houver (por exemplo, o roteiro de um professor)
- Cria uma **identidade visual própria para cada tema**: paleta, tipografia e um elemento memorável
- Usa **animações com propósito**: transições com direção, entradas orquestradas, números que contam, gráficos que crescem e SVG que se desenha
- Entrega um arquivo pronto para abrir no navegador, apresentar e imprimir

## Como usar

1. Crie uma pasta chamada `slides-html` e coloque nela o arquivo `SKILL.md`:

   ```
   slides-html/
   └── SKILL.md
   ```

2. Adicione a pasta (ou o `SKILL.md`) como skill no Claude.
3. Peça os slides em linguagem natural. Exemplos:
   - "Faz slides desse PDF sobre o meu trabalho de sociologia"
   - "Cria uma apresentação de pitch para o meu app de delivery"
   - "Monta um deck sobre energia solar para uma aula"
4. Responda às perguntas de tamanho (quantidade de slides e proporção).
5. Abra o `apresentacao.html` no navegador e apresente.

## Atalhos da apresentação

| Ação | Atalho |
|---|---|
| Próximo / anterior | `→` `←`, espaço, `PageDown` `PageUp` |
| Primeiro / último slide | `Home` / `End` |
| Tela cheia | `F` |
| Visão geral em grade | `G` |
| Pausar animações contínuas | `A` |
| Celular | toque nos botões ou deslize |

Também dá para abrir direto em um slide pela URL, por exemplo `apresentacao.html#3`.

## Direção de arte

A skill evita o visual genérico de IA. Antes de gerar o código, ela monta um plano com:

- **Paleta** de 4 a 6 cores tiradas do universo do tema
- **Tipografia** com fontes do sistema escolhidas com intenção
- **Ideia de layout** em uma frase
- **Um elemento memorável**, com o resto discreto

Ela também segue uma lista de "tells de IA" a evitar, como cards idênticos com a mesma sombra, rótulos em caixa alta acima de todo título, ícones-emoji em cada tópico e o mesmo fade-up em todos os blocos.

## Animações

- Uma família de transição entre slides, escolhida de acordo com o tema
- Entrada do conteúdo em sequência, reiniciada a cada visita ao slide
- Contadores, barras e linhas SVG animados
- Só `transform` e `opacity`, para manter a fluidez
- Respeita `prefers-reduced-motion` e desliga tudo na impressão

## Acessibilidade e impressão

- `lang` configurado, contraste alto e foco visível nos botões
- Contador com `aria-live`
- `@media print` com um slide por página, no mesmo formato escolhido

## Estrutura do repositório

```
.
├── SKILL.md      # a skill
└── README.md     # este arquivo
```

## Licença

Apache-2.0