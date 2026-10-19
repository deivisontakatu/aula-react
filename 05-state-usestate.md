# Aula 5 — Listas e key

## Objetivos de aprendizagem

Compreender como listas de dados são transformadas em elementos React e explicar a finalidade das chaves (key) durante a reconciliação.

## 1. Por que renderizar listas?

Catálogos, listas de tarefas, produtos e resultados de pesquisa são normalmente armazenados como coleções de dados. O React permite transformar essas coleções em elementos de interface de maneira declarativa.

O método JavaScript map() percorre um array e produz um novo array com o resultado de uma função aplicada a cada item.

~~~jsx
const conceitos = ["JSX", "Props", "State"];

const itens = conceitos.map((conceito) => (
  <li>{conceito}</li>
));
~~~

O exemplo demonstra a transformação de dados em elementos, mas ainda precisa de chaves estáveis para cada item.

## 2. O que é key?

key é uma prop especial utilizada pelo React para identificar elementos entre irmãos em uma lista. Ela ajuda o React a reconhecer quais itens foram mantidos, adicionados, removidos ou reordenados.

~~~jsx
const conceitos = [
  { id: "jsx", titulo: "JSX" },
  { id: "props", titulo: "Props" },
  { id: "state", titulo: "State" },
];

const itens = conceitos.map((conceito) => (
  <li key={conceito.id}>{conceito.titulo}</li>
));
~~~

Nesse caso, cada item possui um identificador que funciona como chave.

## 3. O que caracteriza uma boa chave?

Uma boa chave deve ser única entre os elementos irmãos da lista, estável entre renderizações e associada ao item correto ao longo do tempo. Quando os dados possuem um identificador, normalmente ele é a melhor opção. A chave não precisa ser única em toda a aplicação, apenas entre os irmãos relevantes.

## 4. Por que evitar índices como chave?

Usar o índice do array como chave pode funcionar em listas estáticas. Entretanto, em listas que permitem inserção, remoção ou reordenação, os índices podem passar a representar itens diferentes.

Isso pode levar o React a associar estado ou identidade ao item errado. Por esse motivo, prefira identificadores estáveis vindos dos dados.

Também evite gerar chaves aleatórias a cada renderização: isso faz os itens parecerem novos a cada atualização.

## 5. key não é uma prop comum

A chave é utilizada internamente pelo React e não é disponibilizada automaticamente como uma prop comum ao componente filho. Se o componente também precisa do identificador, passe-o separadamente.

~~~jsx
<CardConceito key={conceito.id} id={conceito.id} titulo={conceito.titulo} />
~~~

Aqui, key ajuda o React e id é um dado disponível para o componente.

## 6. Listas e estado

Quando uma lista pode mudar, é importante que a estrutura de dados e as chaves continuem coerentes. Para inserir ou remover itens de um array mantido em estado, a abordagem comum é produzir um novo array, em vez de modificar diretamente o array existente.

## 7. Erros comuns

- Esquecer a key.
- Utilizar identificadores duplicados entre irmãos.
- Usar índices em listas que mudam de ordem.
- Gerar chaves aleatórias a cada renderização.
- Esperar acessar key como uma prop comum no componente filho.

## Resumo

map() permite converter dados em elementos React. key oferece uma identidade estável para cada item e ajuda o React a reconciliar corretamente listas que mudam.

## Para refletir

1. Qual é a finalidade da key?
2. Por que um índice pode ser uma chave inadequada?
3. Por que key não substitui uma prop id?
4. Como chaves estáveis ajudam quando itens são reordenados?

## Referências

- [React — Renderizando listas](https://react.dev/learn/rendering-lists)
- [React — Preservando e redefinindo o estado](https://react.dev/learn/preserving-and-resetting-state)
