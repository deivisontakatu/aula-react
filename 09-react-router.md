# Aula 9 — useEffect

## Objetivos de aprendizagem

Compreender para que serve useEffect, interpretar suas dependências e reconhecer a importância da limpeza de efeitos.

## 1. O que é um efeito?

Um componente React descreve a interface a partir de props e estado. Em alguns casos, além de renderizar a interface, ele precisa sincronizar-se com sistemas externos, como eventos do navegador, temporizadores, conexões, assinaturas, APIs e bibliotecas que não são controladas pelo React.

## 2. O que é useEffect?

useEffect é um Hook que permite sincronizar um componente com sistemas externos. O efeito é declarado por meio de uma função e pode retornar uma função de limpeza.

~~~jsx
import { useEffect } from "react";

useEffect(() => {
  document.title = "React Lab";
}, []);
~~~

Este exemplo define o título da aba do navegador quando o componente é montado, considerando um ambiente de navegador.

## 3. A lista de dependências

A lista de dependências indica os valores reativos utilizados pelo efeito que devem ser acompanhados.

- **Sem lista de dependências:** o efeito é executado após cada renderização confirmada.
- **Lista vazia ([]):** o efeito não depende de valores reativos do componente e, em condições normais, executa na montagem. No desenvolvimento com Strict Mode, o React pode executar um ciclo adicional de configuração e limpeza para ajudar a identificar problemas.
- **Lista com valores ([valor]):** o efeito volta a executar quando uma dependência muda, após a renderização correspondente.

A lista deve refletir os valores reativos utilizados pelo efeito; não é apenas uma configuração escolhida arbitrariamente.

## 4. Limpeza do efeito

Alguns efeitos criam recursos que precisam ser liberados, como ouvintes de eventos ou temporizadores. A função retornada pelo efeito faz essa limpeza.

~~~jsx
useEffect(() => {
  function aoRedimensionar() {
    console.log(window.innerWidth);
  }

  window.addEventListener("resize", aoRedimensionar);

  return () => {
    window.removeEventListener("resize", aoRedimensionar);
  };
}, []);
~~~

A limpeza ocorre antes de uma nova configuração do mesmo efeito quando suas dependências mudam e quando o componente deixa de ser utilizado.

## 5. Quando não usar useEffect

useEffect não é necessário para todo tipo de lógica. Se um valor pode ser calculado diretamente a partir de props e estado durante a renderização, geralmente é melhor fazer esse cálculo diretamente.

Também não é indicado usar efeitos apenas para responder a um clique quando a lógica pertence naturalmente ao manipulador do evento. Efeitos devem atender a uma necessidade real de sincronização externa.

## 6. Efeitos e APIs

Uma requisição de dados pode ser iniciada por um efeito, mas é necessário considerar carregamento, erro, cancelamento ou descarte de respostas obsoletas. Em aplicações maiores, bibliotecas específicas para busca e cache de dados podem oferecer soluções mais completas.

## 7. Erros comuns

- Omitir dependências reativas utilizadas pelo efeito.
- Criar efeitos para cálculos que poderiam ocorrer durante a renderização.
- Esquecer de remover eventos ou limpar temporizadores.
- Supor que um efeito com lista vazia executará literalmente uma única vez em todo ambiente.
- Utilizar useEffect como substituto universal para qualquer lógica de componente.

## Resumo

useEffect sincroniza um componente React com sistemas externos. Entender dependências e limpeza é fundamental para evitar efeitos repetidos desnecessariamente, assinaturas duplicadas e recursos que continuam ativos quando não deveriam.

## Para refletir

1. O que caracteriza um efeito?
2. Para que serve a lista de dependências?
3. Por que alguns efeitos precisam de uma função de limpeza?
4. Quando um cálculo não precisa de useEffect?

## Referências

- [React — Sincronizando com efeitos](https://react.dev/learn/synchronizing-with-effects)
- [React — useEffect](https://react.dev/reference/react/useEffect)
