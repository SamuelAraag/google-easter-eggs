# google-easter-eggs

Um catálogo interativo e **criticamente verificado** de easter eggs, jogos e efeitos visuais acionados por termos digitados na busca do Google (`google.com/search`).

## Por que este repositório existe

Se você procurar "Google easter eggs" na internet, vai encontrar dezenas de listas quase idênticas, muitas geradas ou reescritas por IA, que misturam:

- efeitos que realmente existem hoje;
- efeitos que existiram no passado e foram removidos há anos (ex.: Zerg Rush, Atari Breakout);
- efeitos sazonais apresentados como se estivessem sempre disponíveis;
- sites de terceiros (o mais famoso é a família **elgooG** / **mrdoob.com**) apresentados como se fossem parte do Google — o caso mais comum é o "Google Gravity", que **nunca foi um recurso do google.com**;
- itens que simplesmente não existem mais em nenhuma busca real, mesmo tendo sido citados como "ativos" por várias fontes.

Este projeto tenta separar essas categorias, testando cada item diretamente em `google.com/search` e registrando a data e o método da verificação, em vez de apenas copiar listas existentes.

## Como cada item é verificado

Cada entrada em [`easter-eggs-data.json`](easter-eggs-data.json) é testada manualmente (ou por um agente controlando um navegador real) em `www.google.com/search`, sem estar logado com um histórico de navegação relevante, e o resultado observado é registrado. Quando possível, o termo é testado em mais de uma variação de idioma/região.

### Definição dos status

| Status | Significado |
|---|---|
| `ativo` | Confirmado funcionando na data de verificação, testado diretamente. |
| `sazonal` | Só funciona em datas/eventos específicos (feriados, aniversários, lançamentos). |
| `removido` | Já existiu comprovadamente, mas não foi reproduzido na data de verificação, mesmo com variações do termo. |
| `não confirmado` | Aparece em listas populares ou respostas de IA, mas não foi possível reproduzir de forma confiável. Pode ter sido descontinuado, ser restrito por região/conta, ou nunca ter existido exatamente como descrito. |
| `não é do Google` | O efeito é real, mas roda em um site de terceiros que imita a marca Google (ex.: elgooG, mrdoob.com). Buscar o termo em `google.com/search` não produz o efeito. |

Um item marcado como `não confirmado` **não é necessariamente falso** — só significa que, na data registrada, não foi possível reproduzi-lo. Fontes que afirmam o contrário são listadas no campo `source` de cada item para referência.

## Estrutura de cada item

```json
{
  "id": "identificador-curto",
  "term": "termo exato para pesquisar",
  "category": "categoria (jogo, calculadora, ferramenta, animação, mito...)",
  "effect": "o que deveria acontecer",
  "how_to_test": "instruções passo a passo para reproduzir",
  "status": "ativo | sazonal | removido | não confirmado | não é do Google",
  "verified_date": "AAAA-MM-DD",
  "verification_method": "como e onde foi testado",
  "source": ["fontes consultadas"],
  "notes": "observações sobre idioma, dispositivo, região etc."
}
```

## Catálogo interativo

Abra [`index.html`](index.html) em qualquer navegador (não precisa de servidor) para ver o catálogo com filtros por status e categoria, e busca por termo.

## Limitações conhecidas

- Muitos easter eggs recentes do Google são **painéis de conhecimento promocionais** ligados a filmes, séries, jogos e artistas (ex.: personagens da Marvel, K-pop, lançamentos de streaming). Esses painéis mudam com muita frequência — o que está ativo hoje pode sumir em semanas. Por isso, o catálogo foca principalmente em efeitos **duradouros** (calculadora, jogos clássicos, ferramentas) e trata a categoria de promoções de mídia como especialmente volátil.
- Animações rápidas em CSS/JS (como "do a barrel roll") são difíceis de capturar em uma captura de tela estática feita logo após o carregamento da página, já que a animação termina e a página volta ao estado normal em 1–2 segundos. Nesses casos, o campo `verification_method` explica a limitação.
- Resultados de busca podem variar por conta logada, histórico, região (`gl`), idioma (`hl`) e dispositivo (desktop x mobile). Isso está anotado no campo `notes` quando relevante.

## Como contribuir

Contribuições são bem-vindas, principalmente:

1. **Re-testar itens `não confirmado` ou `removido`** — se você conseguir reproduzir um desses, abra uma issue ou PR com data, idioma/região usados e, se possível, uma captura de tela.
2. **Adicionar novos itens** — siga a estrutura JSON acima. Todo item novo precisa de `verification_method` preenchido; não aceitamos itens copiados de outras listas sem teste próprio.
3. **Atualizar itens desatualizados** — se um item `ativo` parou de funcionar, atualize o status e explique como você testou.

Não aceite de graça a palavra de nenhuma lista (incluindo esta) — teste você mesmo antes de confiar.

## Aviso

Este é um projeto de catalogação sem qualquer vínculo com o Google/Alphabet. "Google" é marca registrada da Google LLC. Sites de terceiros mencionados (como elgooG e mrdoob.com) são citados apenas para fins de identificação e não são endossados por este projeto.

## Licença

MIT — veja [LICENSE](LICENSE).
