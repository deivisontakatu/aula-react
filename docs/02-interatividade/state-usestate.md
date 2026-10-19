# State e useState

## 1. Objetivos de aprendizagem

- Explicar o que é estado em um componente.
- Utilizar o Hook `useState`.
- Atualizar a interface por meio de interações.
- Diferenciar uma variável comum do estado React.

## 2. O problema

Uma variável JavaScript comum pode guardar um valor, mas mudar essa variável não solicita, por si só, uma nova renderização do componente. Para valores que participam da interface e precisam mudar ao longo do uso, podemos usar estado.

## 3. Conceito

O Hook `useState` permite adicionar estado a um componente funcional. Ele retorna o valor atual e uma função que solicita sua atualização.

## 4. Demonstração do professor

```jsx
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Contagem: {count}</p>
      <button onClick={() => setCount(count + 1)}>
        Incrementar
      </button>
    </div>
  );
}
```

Mostre a renderização inicial, o clique, a solicitação de atualização e a mudança na interface. Explique que atualizações de estado são agendadas e que a variável da renderização atual não se altera imediatamente.

## 5. Reprodução do aluno

1. Crie o componente `Counter`.
2. Importe `useState`.
3. Inicialize o contador com zero.
4. Exiba o valor na interface.
5. Adicione um botão para incrementar.
6. Execute e teste.

## 6. Desafio prático

Adicione botões para incrementar e decrementar. O contador não deve ficar abaixo de zero. Inclua também um botão para reiniciar o valor.

## 7. Erros comuns

- Esquecer de importar `useState`.
- Alterar uma variável comum esperando que o React renderize novamente.
- Modificar o estado diretamente quando ele contém objetos ou arrays.
- Chamar Hooks dentro de condições, loops ou funções aninhadas.

## 8. Checklist

- [ ] Entendi o conceito de estado.
- [ ] Implementei o contador.
- [ ] Testei as interações.
- [ ] Resolvi o desafio.

## 9. Próximo passo

Estude eventos para responder a cliques, digitação e outras interações do usuário.
