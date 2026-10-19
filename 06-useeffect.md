# Aula 6 — Renderização condicional

## Objetivos de aprendizagem

Compreender como exibir interfaces diferentes de acordo com condições, utilizar operadores JavaScript em JSX e escolher uma estratégia clara para cada situação.

## 1. O que é renderização condicional?

Renderização condicional é a prática de mostrar, ocultar ou alterar partes da interface conforme uma condição. Por exemplo, uma aplicação pode apresentar uma mensagem de boas-vindas para uma pessoa autenticada, um aviso quando não há resultados ou um indicador enquanto os dados são carregados.

Como JSX permite expressões JavaScript, podemos aproveitar operadores e condições para definir o que será exibido.

## 2. Usando if e return

Quando a condição define partes substancialmente diferentes da interface, uma instrução `if` antes do `return` pode deixar o componente mais legível.

~~~jsx
function MensagemAcesso({ autenticado }) {
  if (autenticado) {
    return <p>Bem-vindo de volta!</p>;
  }

  return <p>Entre para continuar.</p>;
}
~~~

A função retorna uma interface diferente de acordo com o valor recebido por prop.

## 3. Operador ternário

O operador ternário é útil quando queremos escolher entre duas expressões dentro do JSX.

~~~jsx
function Status({ disponivel }) {
  return (
    <p>
      {disponivel ? "Disponível" : "Indisponível"}
    </p>
  );
}
~~~

Use-o para condições simples. Ternários aninhados podem dificultar a leitura e normalmente merecem ser substituídos por condições mais explícitas.

## 4. Operador lógico &&

O operador `&&` pode renderizar um elemento somente quando uma condição for verdadeira.

~~~jsx
function Aviso({ temErro }) {
  return (
    <section>
      {temErro && <p>Não foi possível concluir a operação.</p>}
    </section>
  );
}
~~~

Atenção: se a condição à esquerda for um número como `0`, o JavaScript pode renderizar esse zero. Quando a condição depende de um número, faça uma comparação explícita, como `quantidade > 0 && ...`.

## 5. Combinação com listas e estado

A renderização condicional aparece com frequência junto de listas e estado. Por exemplo, um catálogo pode mostrar uma mensagem quando o array está vazio ou exibir os resultados quando existem itens. A condição deve representar claramente o estado real dos dados.

## 6. Boas práticas

- Prefira condições simples e fáceis de entender.
- Extraia trechos complexos para componentes menores quando isso melhorar a leitura.
- Não confunda ocultar um elemento com proteger dados: regras de autorização precisam ser aplicadas também no servidor.
- Trate explicitamente estados relevantes, como carregamento, erro e lista vazia.
- Evite ternários profundamente aninhados.

## 7. Erros comuns

- Usar `&&` com um número que pode ser zero e acabar exibindo `0`.
- Misturar muitas condições em uma única expressão JSX.
- Esquecer o caso alternativo de uma condição importante.
- Acreditar que esconder um botão na interface substitui a validação de permissões no servidor.

## Resumo

A renderização condicional permite adaptar a interface aos dados, ao estado e às permissões de apresentação. `if`, o operador ternário e `&&` resolvem a maioria dos casos introdutórios; escolha a forma que deixar o código mais claro.

## Para refletir

1. Quando usar `if` em vez de um operador ternário?
2. Qual cuidado é necessário ao usar `&&` com números?
3. Por que esconder um elemento não substitui a autorização no servidor?

## Referências

- [React — Renderização condicional](https://react.dev/learn/conditional-rendering)
- [MDN — Operador condicional (ternário)](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Operators/Conditional_operator)
