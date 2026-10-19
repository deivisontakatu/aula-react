# Consumo de APIs

## 1. Objetivos de aprendizagem

- Explicar como uma interface obtém dados de um serviço externo.
- Reconhecer os estados de carregamento, sucesso e erro.
- Usar `fetch` de forma introdutória com tratamento de falhas.

## 2. O problema

Uma aplicação não precisa manter todos os dados localmente. Muitas vezes, ela consulta um servidor para receber usuários, produtos ou repositórios. A resposta é assíncrona e pode falhar.

## 3. Conceito

A função `fetch` permite realizar requisições HTTP. Como o resultado é assíncrono, a interface deve representar estados como carregamento, dados disponíveis e erro. Em componentes React, a sincronização com uma API pode ser feita com efeitos ou com ferramentas específicas de busca de dados, dependendo da aplicação.

## 4. Demonstração do professor

```jsx
import { useEffect, useState } from "react";

function Users() {
  const [users, setUsers] = useState([]);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState("");

  useEffect(() => {
    let active = true;

    async function loadUsers() {
      try {
        const response = await fetch("https://jsonplaceholder.typicode.com/users");
        if (!response.ok) throw new Error("Falha ao carregar usuários.");
        const data = await response.json();
        if (active) setUsers(data);
      } catch (err) {
        if (active) setError(err.message || "Ocorreu um erro.");
      } finally {
        if (active) setLoading(false);
      }
    }

    loadUsers();
    return () => { active = false; };
  }, []);

  if (loading) return <p>Carregando...</p>;
  if (error) return <p role="alert">{error}</p>;
  return <ul>{users.map((user) => <li key={user.id}>{user.name}</li>)}</ul>;
}
```

Explique cada estado e observe que, em aplicações reais, também é possível cancelar requisições com `AbortController`. Para projetos maiores, considere bibliotecas de busca e cache de dados.

## 5. Reprodução do aluno

1. Crie estados para dados, carregamento e erro.
2. Faça uma requisição com `fetch`.
3. Verifique `response.ok` antes de interpretar os dados.
4. Converta a resposta com `response.json()`.
5. Exiba os dados com `map()` e chaves estáveis.
6. Teste o comportamento quando a requisição falha.

## 6. Desafio prático

Consuma uma API pública de sua escolha e exiba um pequeno conjunto de registros. Inclua estados de carregamento e erro.

## 7. Erros comuns

- Não verificar se a resposta HTTP foi bem-sucedida.
- Esquecer de tratar erros de rede.
- Renderizar dados antes de estarem disponíveis.
- Fazer requisições repetidas por dependências incorretas ou por lógica de efeito mal configurada.
- Expor segredos de API no código do cliente.

## 8. Checklist

- [ ] Entendo o fluxo de uma requisição.
- [ ] Exibo carregamento, sucesso e erro.
- [ ] Renderizo dados externos com chaves estáveis.

## 9. Próximo passo

Consolide os conceitos em uma proposta de projeto integrador.
