# Renderização condicional

## 1. Objetivos de aprendizagem

- Exibir elementos conforme uma condição.
- Utilizar operadores JavaScript no JSX.
- Criar estados visuais simples, como carregando, vazio e concluído.

## 2. O problema

A interface frequentemente depende de dados ou escolhas do usuário: detalhes podem estar ocultos, uma lista pode estar vazia ou uma ação pode ter sido concluída. A renderização condicional permite descrever esses cenários.

## 3. Conceito

Como JSX usa expressões JavaScript, podemos utilizar condições antes do `return`, o operador ternário ou `&&` para escolher o que será exibido. A escolha deve deixar o resultado claro e fácil de manter.

## 4. Demonstração do professor

```jsx
function Status({ concluido }) {
  if (concluido) {
    return <span>Conceito concluído</span>;
  }

  return <span>Conceito pendente</span>;
}
```

Compare com uma expressão ternária dentro do JSX para um exemplo curto.

## 5. Reprodução do aluno

1. Crie um componente que recebe a prop `concluido`.
2. Mostre um texto diferente para cada situação.
3. Crie uma condição para uma lista vazia.
4. Adicione um botão de mostrar/ocultar detalhes, combinado com estado.

## 6. Desafio prático

Crie um card que apresente um selo “Concluído” quando o conceito estiver finalizado e “Em andamento” nos demais casos.

## 7. Erros comuns

- Usar condições aninhadas demais em uma única expressão.
- Esquecer que `&&` pode renderizar o número zero quando o lado esquerdo for zero.
- Duplicar muito conteúdo em vez de extrair partes reutilizáveis.

## 8. Checklist

- [ ] Sei exibir conteúdo condicionalmente.
- [ ] Consigo representar estados diferentes da interface.
- [ ] Escolho uma forma de condição que continua legível.

## 9. Próximo passo

Renderize coleções de dados utilizando `map()` e `key`.
