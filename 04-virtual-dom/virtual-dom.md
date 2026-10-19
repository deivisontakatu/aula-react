# Aula 4 — Virtual DOM

## Objetivos de aprendizagem

Compreender a ideia de Virtual DOM, explicar a reconciliação em termos introdutórios e distinguir renderização de atualização do DOM do navegador.

## 1. O que é o DOM?

O DOM (Document Object Model) é a representação estruturada do documento HTML disponibilizada pelo navegador. JavaScript pode consultar e modificar essa estrutura para alterar textos, atributos, estilos e elementos.

Em uma interface complexa, coordenar manualmente todas as alterações do DOM pode espalhar a lógica de atualização pelo código.

## 2. O que significa Virtual DOM?

Virtual DOM é um termo usado para descrever uma representação em memória da interface. O React utiliza descrições de elementos para determinar como a interface deve se apresentar em determinado momento.

Em vez de exigir que o desenvolvedor indique manualmente cada alteração visual, o modelo declarativo permite descrever o resultado esperado a partir das props e do estado. O React coordena o processo de atualização.

O termo é útil para uma explicação introdutória, mas não deve ser entendido como uma cópia literal, permanente e completa do DOM do navegador em todos os detalhes.

## 3. Renderização e reconciliação

De maneira simplificada, o processo pode ser descrito assim:

1. Uma interação ou atualização de dados solicita uma mudança.
2. O React executa novamente os componentes relevantes para calcular a nova descrição da interface.
3. O React compara essa descrição com a anterior — processo associado à reconciliação.
4. As alterações necessárias são aplicadas ao ambiente de renderização, como o DOM do navegador.

Essa sequência é um modelo mental para aprendizagem. Os detalhes internos dependem do contexto de renderização e da implementação do React.

## 4. Exemplo conceitual

Imagine um contador que mostra o número zero. Ao clicar em “Incrementar”, o estado passa a representar um.

O desenvolvedor descreve o texto como dependente do estado. O React calcula a nova descrição e coordena a atualização necessária para que a interface apresente o novo valor.

Não é necessário que o desenvolvedor localize manualmente o parágrafo e substitua seu texto por meio de uma chamada direta ao DOM.

## 5. O Virtual DOM torna tudo mais rápido?

Não se deve afirmar que o Virtual DOM torna automaticamente qualquer aplicação mais rápida. O desempenho depende da estrutura dos componentes, dos cálculos executados, do volume de dados e de outros fatores.

O principal benefício para o desenvolvimento é a abordagem declarativa e a coordenação das atualizações. Otimizações devem ser feitas com base em evidências e medições.

## 6. Reconciliação e identidade

O React também precisa identificar quais elementos representam a mesma parte lógica da interface entre renderizações. O tipo do elemento, sua posição na árvore e as chaves usadas em listas ajudam nesse processo.

Uma chave estável pode ajudar o React a associar um item à sua identidade lógica quando uma lista muda.

## 7. DOM direto e React

Há situações legítimas para acessar o DOM diretamente, por exemplo, para focar um campo. Porém, alterações diretas em elementos gerenciados pelo React podem causar inconsistências se forem usadas como substitutas do fluxo normal de estado e renderização.

## Erros comuns

- Afirmar que o React recria toda a página em cada atualização.
- Tratar o Virtual DOM como uma cópia exata e permanente do DOM real.
- Supor que Virtual DOM garante melhor desempenho em qualquer cenário.
- Confundir a renderização de componentes com a atualização de todos os nós do DOM.

## Resumo

Virtual DOM é um modelo mental útil para entender como o React trabalha com descrições da interface e reconcilia mudanças. O desenvolvedor declara o resultado esperado; o React coordena as atualizações necessárias.

## Para refletir

1. Qual é a diferença entre DOM e Virtual DOM?
2. O que significa reconciliação?
3. Por que não podemos garantir que toda aplicação React será mais rápida apenas por usar Virtual DOM?

## Referências

- [React — Renderização e confirmação](https://react.dev/learn/render-and-commit)
- [React — Preservando e redefinindo o estado](https://react.dev/learn/preserving-and-resetting-state)
