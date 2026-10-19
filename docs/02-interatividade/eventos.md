# Eventos

## 1. Objetivos de aprendizagem

- Responder a eventos do usuário.
- Utilizar props de evento como `onClick` e `onChange`.
- Entender a diferença entre passar uma função e chamar uma função durante a renderização.

## 2. O problema

Interfaces úteis precisam responder às ações das pessoas: clicar em um botão, digitar em um campo ou enviar um formulário. O React oferece props de evento para conectar essas ações às funções.

## 3. Conceito

Eventos são tratados passando uma função para uma prop como `onClick`. O React chama essa função quando o evento ocorre. Em JSX, normalmente escrevemos `onClick={handleClick}`, em vez de `onClick={handleClick()}`, que executaria a chamada durante a renderização.

## 4. Demonstração do professor

```jsx
function AlertButton() {
  function handleClick() {
    alert("Você clicou no botão!");
  }

  return <button onClick={handleClick}>Clique aqui</button>;
}
```

Em seguida, demonstre `onChange` em um campo de texto e explique como obter o valor do evento.

## 5. Reprodução do aluno

1. Crie um botão com `onClick`.
2. Escreva uma função manipuladora.
3. Faça o botão mostrar uma mensagem.
4. Crie um campo de texto com `onChange`.
5. Exiba ou registre o valor digitado.

## 6. Desafio prático

Implemente um botão que alterna entre “Mostrar detalhes” e “Ocultar detalhes”. Use estado para guardar a opção selecionada.

## 7. Erros comuns

- Chamar a função diretamente em vez de passar a referência, quando a intenção é executar no evento.
- Escrever nomes de evento com capitalização incorreta.
- Colocar código complexo diretamente no JSX, dificultando leitura e manutenção.

## 8. Checklist

- [ ] Sei associar uma função a um evento.
- [ ] Consigo tratar cliques e alterações de campos.
- [ ] Entendo quando a função será executada.

## 9. Próximo passo

Aplique eventos e estado à renderização condicional.
