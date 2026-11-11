# Teste de API — kits de produtos e entrega

Projeto da Sprint 4 do curso de QA Engineer da TripleTen: teste manual de API REST com o **Postman**, com casos de teste positivos e negativos para dois endpoints e relatórios de bug no Jira.

## Objetivo

Verificar se dois endpoints da API seguem as regras de negócio da documentação e se tratam corretamente dados válidos, inválidos, vazios e ausentes.

## Endpoints testados

1. **`POST /api/v1/kits/:id/products`** — adiciona produtos a um kit.
   Testes com ID de kit e de produto válidos e inválidos (string, vazio, null, caracteres especiais, número negativo, valor muito longo), `productsList` vazia ou como objeto, `quantity` com tipos inválidos, corpo da requisição ausente e limite de 30 itens por kit.
2. **`POST /order-and-go/v1/delivery`** — calcula a entrega do serviço "Order and Go".
   Testes de valores limite para horário de entrega (`deliveryTime`), quantidade (`productsCount`) e peso (`productsWeight`), custo da entrega e campos com tipos inválidos, vazios ou ausentes.

## Resultados

| Endpoint | Casos de teste | Aprovados | Reprovados |
|---|---|---|---|
| `POST /api/v1/kits/:id/products` | 26 | 7 | 19 |
| `POST /order-and-go/v1/delivery` | 41 | 19 | 22 |
| **Total** | **67** | **26** | **41** |

Cada caso reprovado gerou um relatório de bug no Jira (SPRINT04-1 a SPRINT04-41).

### Exemplos de bugs encontrados

- A API retorna **500 Internal Server Error** em vez de **400 Bad Request** quando recebe ID ou `quantity` com tipo inválido.
- A API aceita com **200 OK** requisições sem corpo, com `productsList` vazia ou com `quantity` negativa.
- O endpoint de entrega aceita `productsCount` e `productsWeight` negativos ou iguais a 0.
- O endpoint de entrega retorna `"isItPossibleToDeliver": true` fora do horário permitido (`deliveryTime` 7 e 23).
- O custo da entrega (`clientDeliveryCost`) é calculado errado em alguns limites de quantidade e peso.

## Arquivos

- [`casos-de-teste-api.xlsx`](casos-de-teste-api.xlsx): planilha com uma aba para cada endpoint. Cada caso tem título, etapas, dados do teste (corpo da requisição), resultado esperado, resultado real, status e link para o bug.
- [`BUGS.md`](BUGS.md): os 41 relatórios de bug copiados do Jira, com o comando cURL de cada requisição, resultado esperado e resultado real.

## O que aprendi

- **HTTP:** métodos, códigos de status (200, 400, 404, 405, 500) e estrutura de requisições e respostas.
- **Teste de API:** criar casos positivos e negativos a partir da documentação, usando classes de equivalência e valores limite.
- **Postman:** enviar requisições, montar o corpo em JSON e conferir as respostas.
- **Relatórios de bug de API:** incluir o endpoint no título, o cURL completo, o resultado esperado e o resultado real.
