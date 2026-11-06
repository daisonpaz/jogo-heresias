# Qual é a sua heresia?

> Um quiz de sim ou não sobre heresias e doutrina católica, com humor e material de estudo.

O jogador responde a perguntas com apenas duas opções, **sim** ou **não**. Conforme as respostas, pode ser "enquadrado" em uma ou mais heresias da história da Igreja. No final, o jogo mostra uma mensagem bem-humorada, um placar e textos de aprofundamento (origem histórica do erro e razões doutrinárias e bíblicas que o explicam) sobre cada heresia em que a pessoa caiu.

O projeto também é um **exercício para o aprendizado de programação**: o código é simples, comentado e organizado para ser lido por quem está começando.

## Como jogar

- **Online:** [https://daisonpaz.github.io/jogo-heresias](https://daisonpaz.github.io/jogo-heresias/)
- **No seu computador ou celular:** baixe este repositório e abra o arquivo `index.html` no navegador. Não é preciso instalar nada.

## O que o jogo tem hoje

- 14 perguntas de sim ou não
- 7 heresias: Arianismo, Docetismo, Pelagianismo, Iconoclastia, Nestorianismo, Monofisismo e Modalismo
- Mensagens finais que variam conforme o número de heresias acumuladas
- Painéis "Para aprofundar" com contexto histórico, doutrinário e base bíblica

Como cada resposta soma pontos, o resultado pode apontar nenhuma heresia, uma ou várias. As respostas ortodoxas ficam misturadas entre "sim" e "não" de propósito, para quem responder sempre a mesma opção não leve a lugar nenhum.

## Como adicionar conteúdo

Todo o conteúdo fica no bloco **DADOS**, no início do `<script>` do `index.html`. Não é preciso mexer na lógica do jogo.

**Nova pergunta:** acrescente um item à lista `perguntas`. Cada resposta diz quantos pontos dá a cada heresia (`{}` significa que a resposta é ortodoxa).

```js
{
  texto: `Em Cristo há uma só pessoa, a do Filho de Deus, que nasceu de Maria.`,
  sim: {},                       // resposta ortodoxa: nenhum ponto
  nao: { nestorianismo: 2 }      // resposta herética: 2 pontos
}
```

**Nova heresia:** acrescente um item a `heresias`, com o nome e o texto de aprofundamento, e escreva as perguntas que pontuam nela.

```js
modalismo: {
  nome: `Modalismo`,
  texto: `Contexto histórico, concílio que respondeu e base bíblica...`
}
```

> **Atenção:** hoje o placar assume **no máximo 4 pontos por heresia**, ou seja, duas perguntas de 2 pontos para cada uma. Se você mudar isso, ajuste também a lógica de exibição do placar. Os detalhes estão em [`docs/EVOLUCAO.md`](docs/EVOLUCAO.md), seção 3.4.

## Estrutura do repositório

```text
.
├── index.html          # O jogo inteiro (HTML, CSS e JavaScript)
├── README.md           # Esta página
├── LICENSE             # Licença MIT
└── docs/
    └── EVOLUCAO.md     # Como o projeto evoluiu, changelog e decisões de arquitetura
```

## Documentação

A história do projeto, o histórico de versões e as decisões de arquitetura estão em [`docs/EVOLUCAO.md`](docs/EVOLUCAO.md).

## Aviso

- Este é um projeto **independente e didático**, sem vínculo oficial com a Igreja Católica nem com qualquer instituição.
- O humor visa **ideias**, não pessoas. É só um jogo: ninguém merece fogueira por errar uma pergunta de teologia.
- Os textos de aprofundamento foram redigidos com base em conhecimento geral e devem ser conferidos nas fontes ([Catecismo da Igreja Católica, Direito Canônico e atas dos concílios](https://www.vatican.va/archive/index_po.htm)) antes de qualquer uso mais sério.
- Não fique com **dúvidas e angústias**, vá à paróquia mais próxima e procure um diretor espiritual. 

## Assistência de IA
- Parte do código e a organização da documentação foram auxiliados pelo Claude (Sonnet 5.5).
- Todos os blocos gerados por IA foram revisados, testados e adaptados manualmente pelo autor.

## Contribuindo

Sugestões e correções são bem-vindas, principalmente de conteúdo doutrinário ou histórico. Ao abrir uma *issue* ou um *pull request*, indique a fonte que sustenta a correção.

## Licença

Distribuído sob a licença MIT. Veja o arquivo [`LICENSE`](LICENSE).
