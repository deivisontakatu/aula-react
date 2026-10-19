# Aula 10 — Consumo de APIs

## Objetivos de aprendizagem

Entender o papel de uma API em uma aplicação React, reconhecer o fluxo de uma requisição HTTP e identificar os estados necessários para apresentar dados externos de forma confiável.

## 1. O que é uma API?

API (Application Programming Interface) é uma interface que define como sistemas ou componentes de software se comunicam. Em aplicações web, uma API HTTP frequentemente disponibiliza recursos por meio de URLs e métodos como GET, POST, PUT, PATCH e DELETE.

Uma aplicação React pode consumir uma API para buscar produtos, usuários, publicações, indicadores ou qualquer outro dado disponibilizado por um serviço.

## 2. O fluxo básico de uma requisição

1. A aplicação envia uma requisição HTTP.
2. O servidor processa a solicitação.
3. O servidor retorna uma resposta com um status e, frequentemente, dados.
4. A aplicação interpreta a resposta.
5. O React apresenta os dados conforme o estado da interface.

As respostas JSON são comuns, mas uma API também pode devolver outros formatos.

## 3. A função fetch

A função fetch disponibilizada pelo navegador permite realizar requisições HTTP. Como a comunicação ocorre de forma assíncrona, o código precisa aguardar a resposta e tratar possíveis falhas.

~~~jsx
const resposta = await fetch("https://api.exemplo.com/conceitos");

if (!resposta.ok) {
  throw new Error("Não foi possível carregar os conceitos.");
}

const dados = await resposta.json();
~~~

O exemplo é ilustrativo: o endereço precisa ser substituído por uma API real e acessível. Também é importante verificar o status HTTP; fetch não rejeita automaticamente a Promise para todos os códigos de erro HTTP, como 404 ou 500.

## 4. Estados da interface

Uma interface que depende de uma API normalmente precisa representar pelo menos três situações:

- **Carregando:** a requisição ainda não terminou.
- **Sucesso:** os dados foram recebidos e podem ser exibidos.
- **Erro:** a requisição falhou ou a resposta não pôde ser processada.

Também é útil considerar o estado vazio, quando a consulta foi bem-sucedida, mas não retornou registros. Representar esses estados torna a aplicação mais clara e evita deixar a pessoa sem feedback durante a espera.

## 5. Como React participa desse processo?

Os dados recebidos normalmente são armazenados em estado ou gerenciados por uma biblioteca de busca de dados. Quando o estado muda, o React pode renderizar a interface correspondente.

Uma consulta pode ser iniciada por um efeito quando a necessidade é sincronizar o componente com uma fonte externa. Em aplicações mais complexas, ferramentas específicas podem oferecer cache, repetição, cancelamento e sincronização de dados de forma mais robusta.

## 6. Cuidados importantes

- Verifique response.ok e trate erros de rede.
- Considere tempo de espera, cancelamento e respostas que chegam fora de ordem.
- Não exponha chaves secretas ou credenciais privadas no código enviado ao navegador.
- Respeite limites de uso, autenticação e políticas da API.
- Trate os dados recebidos como entrada externa e valide-os conforme a necessidade.
- Não assuma que a conexão estará sempre disponível.
- Considere CORS: o navegador pode bloquear certas requisições conforme a política do servidor.

## 7. API pública e ambiente de desenvolvimento

APIs públicas são úteis para fins educacionais, mas podem mudar, limitar requisições ou ficar indisponíveis. Para aulas, escolha uma API documentada, estável e apropriada ao objetivo didático. Verifique antecipadamente se ela permite as requisições necessárias a partir do navegador.

## 8. Erros comuns

- Não verificar o status da resposta.
- Não tratar erros de rede.
- Exibir dados antes de estarem disponíveis.
- Fazer requisições repetidas devido a dependências incorretas em efeitos.
- Ignorar carregamento e estado vazio.
- Incluir segredos no código do cliente.
- Supor que toda API aceita requisições de qualquer origem.

## Resumo

O consumo de APIs permite que uma interface React trabalhe com dados externos. Para uma experiência robusta, é essencial compreender requisições assíncronas, tratar erros e representar os estados de carregamento, sucesso e ausência de dados.

## Para refletir

1. Qual é o papel de uma API em uma aplicação web?
2. Por que é importante verificar response.ok?
3. Quais estados a interface deve representar durante uma consulta?
4. O que é CORS?
5. Por que credenciais secretas não devem ficar no código do navegador?

## Referências

- [MDN — Fetch API](https://developer.mozilla.org/docs/Web/API/Fetch_API)
- [MDN — Usando Fetch](https://developer.mozilla.org/docs/Web/API/Fetch_API/Using_Fetch)
- [React — Sincronizando com efeitos](https://react.dev/learn/synchronizing-with-effects)

## Exemplos adicionais de código

Os exemplos usam o endpoint público `https://jsonplaceholder.typicode.com` para fins didáticos. Verifique a disponibilidade do serviço antes da aula.

### Exemplo 1 — Buscar dados com fetch
~~~jsx
async function buscarPublicacoes() {
  const resposta = await fetch("https://jsonplaceholder.typicode.com/posts");

  if (!resposta.ok) {
    throw new Error("Falha ao buscar publicações.");
  }

  return resposta.json();
}
~~~

### Exemplo 2 — Carregamento, erro e sucesso
~~~jsx
import { useEffect, useState } from "react";

function ListaPublicacoes() {
  const [publicacoes, setPublicacoes] = useState([]);
  const [carregando, setCarregando] = useState(true);
  const [erro, setErro] = useState("");

  useEffect(() => {
    async function carregar() {
      try {
        const resposta = await fetch("https://jsonplaceholder.typicode.com/posts");
        if (!resposta.ok) throw new Error("Não foi possível carregar.");
        setPublicacoes(await resposta.json());
      } catch (erroRecebido) {
        setErro(erroRecebido.message);
      } finally {
        setCarregando(false);
      }
    }

    carregar();
  }, []);

  if (carregando) return <p>Carregando...</p>;
  if (erro) return <p role="alert">{erro}</p>;

  return (
    <ul>
      {publicacoes.slice(0, 5).map((item) => (
        <li key={item.id}>{item.title}</li>
      ))}
    </ul>
  );
}
~~~

### Exemplo 3 — Enviar dados com POST
~~~jsx
async function criarPublicacao() {
  const resposta = await fetch("https://jsonplaceholder.typicode.com/posts", {
    method: "POST",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify({
      title: "Aprendendo React",
      body: "Exemplo didático de envio de dados",
      userId: 1
    })
  });

  if (!resposta.ok) {
    throw new Error("Não foi possível criar a publicação.");
  }

  const novaPublicacao = await resposta.json();
  return novaPublicacao;
}
~~~
