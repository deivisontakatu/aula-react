# Formulários

## 1. Objetivos de aprendizagem

- Criar formulários em componentes React.
- Entender campos controlados.
- Tratar o envio e validar uma entrada simples.

## 2. O problema

Formulários recebem dados dos usuários. Em aplicações React, muitas vezes precisamos manter os valores dos campos sincronizados com o estado para validar, transformar e utilizar esses dados.

## 3. Conceito

Em um campo controlado, o valor exibido vem do estado React e as alterações atualizam esse estado por meio de um manipulador. O envio de um formulário pode ser tratado com `onSubmit`; `event.preventDefault()` evita o comportamento padrão de navegação quando a aplicação fará o tratamento por conta própria.

## 4. Demonstração do professor

```jsx
import { useState } from "react";

function ConceptForm() {
  const [titulo, setTitulo] = useState("");

  function handleSubmit(event) {
    event.preventDefault();
    alert(`Conceito cadastrado: ${titulo}`);
  }

  return (
    <form onSubmit={handleSubmit}>
      <label htmlFor="titulo">Título</label>
      <input
        id="titulo"
        value={titulo}
        onChange={(event) => setTitulo(event.target.value)}
      />
      <button type="submit">Cadastrar</button>
    </form>
  );
}
```

Explique o fluxo campo → evento → estado → valor renderizado.

## 5. Reprodução do aluno

1. Crie um campo de título.
2. Guarde seu valor usando `useState`.
3. Sincronize o campo com o estado.
4. Trate o envio do formulário.
5. Apresente uma mensagem com os dados enviados.

## 6. Desafio prático

Acrescente um campo de descrição e impeça o envio quando o título estiver vazio. Exiba uma mensagem de validação compreensível.

## 7. Erros comuns

- Misturar `value` controlado com lógica de atualização ausente.
- Esquecer `event.preventDefault()` quando necessário.
- Não associar um `label` ao campo.
- Tratar validação no navegador como substituta da validação necessária no servidor.

## 8. Checklist

- [ ] Sei criar um campo controlado.
- [ ] Consigo tratar o envio.
- [ ] Implementei validação simples.

## 9. Próximo passo

Organize vários registros com listas e atribua uma chave estável a cada elemento.
