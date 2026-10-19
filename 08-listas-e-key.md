# Aula 8 — Formulários em React

## Objetivos de aprendizagem

Entender como formulários recebem dados, compreender campos controlados e reconhecer os principais cuidados de acessibilidade e validação.

## 1. O papel dos formulários

Formulários permitem que usuários enviem informações para uma aplicação. Podem servir para cadastrar conceitos, filtrar conteúdos, autenticar pessoas ou registrar preferências.

Em React, os formulários combinam elementos HTML com eventos e, quando necessário, estado para acompanhar os dados inseridos.

## 2. Campos controlados

Um campo controlado é aquele cujo valor é definido pelo estado React. O evento de alteração atualiza esse estado, mantendo o valor exibido sincronizado com os dados do componente.

~~~jsx
import { useState } from "react";

function CampoNome() {
  const [nome, setNome] = useState("");

  return (
    <label>
      Nome
      <input
        value={nome}
        onChange={(evento) => setNome(evento.target.value)}
      />
    </label>
  );
}
~~~

Nesse exemplo, value define o valor exibido e onChange informa ao React sobre as alterações feitas pela pessoa.

## 3. Envio do formulário

O evento onSubmit permite tratar o envio. Quando a aplicação pretende processar os dados sem a navegação padrão do navegador, é comum chamar event.preventDefault() no manipulador.

~~~jsx
function aoEnviar(evento) {
  evento.preventDefault();
  // Processar os dados do formulário.
}
~~~

A lógica de envio pode validar os campos, apresentar mensagens e encaminhar os dados a um serviço.

## 4. Validação

A validação pode ocorrer em diferentes camadas:

- **HTML:** atributos como required, type="email" e minLength ajudam com validações básicas.
- **Interface React:** permite apresentar mensagens específicas e orientar a pessoa.
- **Servidor:** precisa validar os dados recebidos, pois as verificações no navegador podem ser contornadas.

A validação deve ser compreensível, indicar o problema e ajudar a corrigi-lo.

## 5. Acessibilidade

Formulários acessíveis ajudam as pessoas a compreender e preencher os campos. Boas práticas incluem associar um label a cada campo, usar tipos de entrada adequados, informar erros por texto, preservar foco e ordem lógica de navegação e identificar claramente o botão de envio.

## 6. Campos controlados e não controlados

Em campos controlados, o estado React define o valor do campo. Em campos não controlados, o próprio elemento do DOM mantém o valor e ele pode ser lido quando necessário, por exemplo por meio de uma referência ou da API FormData.

As duas abordagens são válidas em contextos diferentes. A escolha depende da complexidade, da validação e de como os dados serão utilizados.

## 7. Erros comuns

- Definir value sem implementar a atualização correspondente.
- Esquecer de tratar o envio e permitir uma navegação inesperada.
- Não associar rótulos aos campos.
- Validar apenas no cliente quando o dado será processado por um servidor.
- Exibir mensagens genéricas que não ajudam a pessoa a corrigir o problema.

## Resumo

Formulários em React combinam elementos HTML, eventos e, frequentemente, estado. Campos controlados são úteis quando a aplicação precisa acompanhar os valores durante a digitação; validação e acessibilidade devem fazer parte do planejamento desde o início.

## Para refletir

1. O que caracteriza um campo controlado?
2. Qual é a função de onSubmit?
3. Por que a validação do navegador não substitui a validação no servidor?
4. Como tornar um formulário mais acessível?

## Referências

- [React — Respondendo a eventos](https://react.dev/learn/responding-to-events)
- [React — Reagindo à entrada com estado](https://react.dev/learn/reacting-to-input-with-state)
- [MDN — Elemento form](https://developer.mozilla.org/docs/Web/HTML/Element/form)
