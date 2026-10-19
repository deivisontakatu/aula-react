# Aula 5 — State e useState

## Objetivos de aprendizagem

Entender o conceito de estado, reconhecer quando uma informação deve ser armazenada nele e compreender como o Hook useState participa das atualizações da interface.

## 1. O que é estado?

Estado é uma informação que um componente precisa lembrar entre renderizações. Exemplos comuns incluem um contador, a opção selecionada em um filtro, a abertura de um menu e os dados digitados em um formulário.

Quando o estado muda, o React pode renderizar novamente o componente para refletir o novo valor na interface.

## 2. Por que uma variável comum não basta?

Uma variável local pode armazenar um valor durante a execução de uma função, mas alterá-la não solicita, por si só, uma nova renderização. Além disso, a função do componente pode ser executada novamente e recriar suas variáveis locais.

O estado React permite preservar um valor entre renderizações e informar ao React quando uma atualização é necessária.

## 3. O Hook useState

useState permite adicionar estado a um componente funcional. Ele retorna o valor atual e uma função para solicitar sua atualização.

~~~jsx
import { useState } from "react";

function Contador() {
  const [contador, setContador] = useState(0);

  return (
    <section>
      <p>Valor: {contador}</p>
      <button onClick={() => setContador(contador + 1)}>
        Incrementar
      </button>
    </section>
  );
}
~~~

Nesse exemplo, contador representa o valor usado na renderização atual. setContador solicita a atualização para um novo valor.

## 4. O que acontece após uma atualização?

1. A pessoa interage com a interface.
2. Uma função chama o atualizador do estado.
3. O React agenda e processa a atualização.
4. O componente é renderizado novamente com o estado atualizado.
5. O React coordena as alterações necessárias na interface.

A atualização não deve ser entendida como uma mudança imediata da variável local na mesma execução da função.

## 5. Atualizações baseadas no valor anterior

Quando o próximo valor depende do valor anterior, é comum usar a forma funcional do atualizador:

~~~jsx
setContador((valorAnterior) => valorAnterior + 1);
~~~

Essa forma é especialmente útil quando várias atualizações são solicitadas em sequência, porque cada cálculo recebe o valor anterior apropriado da fila de atualizações.

## 6. Estado com objetos e arrays

O estado pode armazenar strings, números, booleanos, objetos e arrays. Ao atualizar objetos e arrays, a abordagem usual é criar uma nova estrutura em vez de modificar diretamente a estrutura existente.

~~~jsx
setPerfil((perfilAtual) => ({
  ...perfilAtual,
  curso: "Análise e Desenvolvimento de Sistemas"
}));
~~~

A imutabilidade ajuda o React a identificar mudanças de referência e torna o fluxo de dados mais previsível.

## 7. Regras dos Hooks

- Chame Hooks no nível superior de componentes funcionais ou de Hooks personalizados.
- Não os chame dentro de condições, loops ou funções aninhadas.
- Use estado para valores que precisam persistir e influenciar a interface.
- Evite duplicar estado quando um valor pode ser calculado a partir de outros dados.

## 8. Erros comuns

- Modificar diretamente objetos ou arrays guardados no estado.
- Esperar que mudar uma variável comum atualize a interface.
- Chamar Hooks condicionalmente.
- Armazenar em estado um valor que pode ser calculado durante a renderização sem necessidade.
- Ignorar que atualizações podem ser agrupadas pelo React.

## Resumo

O estado permite que os componentes mantenham informações ao longo do tempo. useState fornece o valor atual e uma função de atualização, permitindo que a interface responda às interações do usuário.

## Para refletir

1. Qual é a diferença entre estado e uma variável local?
2. Por que devemos evitar mutar objetos guardados no estado?
3. Quando é útil usar a forma funcional de atualização?

## Referências

- [React — Adicionando interatividade](https://react.dev/learn/adding-interactivity)
- [React — useState](https://react.dev/reference/react/useState)
- [React — Atualizando objetos no estado](https://react.dev/learn/updating-objects-in-state)
