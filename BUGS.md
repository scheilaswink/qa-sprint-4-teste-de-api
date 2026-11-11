# Relatórios de bug — Teste de API (Sprint 4)

Os 41 bugs abaixo foram registrados no Jira durante o teste da API. Como o Jira do projeto é privado, eles foram copiados para cá para que qualquer pessoa possa ler os relatórios.

Os IDs (SPRINT04-1 a SPRINT04-41) são os mesmos da coluna "Link para o relatório de bug" da planilha. Os endereços dos servidores nos comandos cURL eram temporários e não funcionam mais.

## Resumo

| ID | Título | Endpoint | Prioridade |
|---|---|---|---|
| [SPRINT04-1](#sprint04-1) | Retorna 500 Internal Server Error ao enviar requisição POST com parâmetro ID do tipo string. | `POST /api/v1/kits/:id/products` | Média |
| [SPRINT04-2](#sprint04-2) | Retorna 500 Internal Server Error ao enviar requisição POST com parâmetro ID vazio. | `POST /api/v1/kits/:id/products` | Média |
| [SPRINT04-3](#sprint04-3) | Retorna 500 Internal Server Error ao enviar requisição POST com parâmetro ID do tipo null. | `POST /api/v1/kits/:id/products` | Média |
| [SPRINT04-4](#sprint04-4) | Retorna 500 Internal Server Error ao enviar requisição POST com parâmetro ID do tipo caractere especial. | `POST /api/v1/kits/:id/products` | Média |
| [SPRINT04-5](#sprint04-5) | Retorna 500 Internal Server Error ao enviar requisição POST com parâmetro ID muito longo. | `POST /api/v1/kits/:id/products` | Média |
| [SPRINT04-6](#sprint04-6) | Retorna 500 Internal Server Error ao enviar requisição POST com parâmetro ID do tipo negativo. | `POST /api/v1/kits/:id/products` | Média |
| [SPRINT04-7](#sprint04-7) | Retorna 500 Internal Server Error ao enviar requisição POST com o "productsList" como um objeto. | `POST /api/v1/kits/:id/products` | Média |
| [SPRINT04-8](#sprint04-8) | Retorna 200 OK ao enviar requisição POST com o ID excluído. | `POST /api/v1/kits/:id/products` | Média |
| [SPRINT04-9](#sprint04-9) | Retorna 200 OK ao enviar requisição POST removendo o Body por completo. | `POST /api/v1/kits/:id/products` | Média |
| [SPRINT04-10](#sprint04-10) | Retorna 200 OK ao enviar requisição POST com o "productsList"vazio. | `POST /api/v1/kits/:id/products` | Média |
| [SPRINT04-11](#sprint04-11) | Retorna 500 Internal Server Error ao enviar requisição POST com o "quantity" do tipo string. | `POST /api/v1/kits/:id/products` | Média |
| [SPRINT04-12](#sprint04-12) | Retorna 200 OK ao enviar requisição POST com o "quantity" vazio. | `POST /api/v1/kits/:id/products` | Média |
| [SPRINT04-13](#sprint04-13) | Retorna 500 Internal Server Error ao enviar requisição POST com o "quantity" do tipo null. | `POST /api/v1/kits/:id/products` | Média |
| [SPRINT04-14](#sprint04-14) | Retorna 500 Internal Server Error ao enviar requisição POST com o "quantity" do tipo caractere especial. | `POST /api/v1/kits/:id/products` | Média |
| [SPRINT04-15](#sprint04-15) | Retorna 500 Internal Server Error ao enviar requisição POST com o "quantity" do tipo muito longo. | `POST /api/v1/kits/:id/products` | Média |
| [SPRINT04-16](#sprint04-16) | Retorna 200 OK ao enviar requisição POST com o "quantity" do tipo negativo. | `POST /api/v1/kits/:id/products` | Média |
| [SPRINT04-17](#sprint04-17) | Retorna 500 Internal Server Error ao enviar requisição POST com o "quantity" excluído. | `POST /api/v1/kits/:id/products` | Média |
| [SPRINT04-18](#sprint04-18) | Retorna 500 Internal Server Error ao enviar requisição POST criando outro ID de kit da URL com uma string. | `POST /api/v1/kits/:id/products` | Média |
| [SPRINT04-19](#sprint04-19) | Retorna 500 Internal Server Error ao enviar requisição POST criando outro ID de kit da URL com caractere especial. | `POST /api/v1/kits/:id/products` | Média |
| [SPRINT04-20](#sprint04-20) | Retorna o parâmetro "isItPossibleToDeliver": true ao enviar requisição POST com o parâmetro "deliveryTime": 7 | `POST /order-and-go/v1/delivery` | Média |
| [SPRINT04-21](#sprint04-21) | Retorna o parâmetro "isItPossibleToDeliver": true ao enviar requisição POST com o parâmetro "deliveryTime": 23 | `POST /order-and-go/v1/delivery` | Média |
| [SPRINT04-22](#sprint04-22) | Retorna 200 OK quando foi enviado o parâmetro "productsCount": -1 | `POST /order-and-go/v1/delivery` | Média |
| [SPRINT04-23](#sprint04-23) | Retorna 200 OK quando foi enviado o parâmetro "productsCount" igual a 0. | `POST /order-and-go/v1/delivery` | Média |
| [SPRINT04-24](#sprint04-24) | Retorna 200 OK quando foi enviado o parâmetro "productsCount" igual a 16 | `POST /order-and-go/v1/delivery` | Média |
| [SPRINT04-25](#sprint04-25) | Retorna 200 OK quando foi enviado o parâmetro "productsWeight" é igual a -1 | `POST /order-and-go/v1/delivery` | Média |
| [SPRINT04-26](#sprint04-26) | Retorna 200 OK quando foi enviado o parâmetro "productsWeight" é igual a 0 | `POST /order-and-go/v1/delivery` | Média |
| [SPRINT04-27](#sprint04-27) | Retorna 200 OK quando foi enviado o parâmetro "productsWeight" é igual a 3.1 | `POST /order-and-go/v1/delivery` | Média |
| [SPRINT04-28](#sprint04-28) | Retorna 200 OK quando foi enviado o parâmetro "productsWeight" é igual a 6.1 | `POST /order-and-go/v1/delivery` | Média |
| [SPRINT04-29](#sprint04-29) | Retorna 200 OK quando foi enviado o parâmetro "productsWeight" do tipo null | `POST /order-and-go/v1/delivery` | Média |
| [SPRINT04-30](#sprint04-30) | Retorna 200 OK quando foi enviado o parâmetro "productsWeight" do tipo string | `POST /order-and-go/v1/delivery` | Média |
| [SPRINT04-31](#sprint04-31) | Retorna 200 OK quando foi enviado o parâmetro "productsWeight" do tipo caractere | `POST /order-and-go/v1/delivery` | Média |
| [SPRINT04-32](#sprint04-32) | Retorna 200 OK quando foi enviado o parâmetro "productsWeight" vazio | `POST /order-and-go/v1/delivery` | Média |
| [SPRINT04-33](#sprint04-33) | Retorna 200 OK quando foi enviado o parâmetro "deliveryTime" como uma string | `POST /order-and-go/v1/delivery` | Média |
| [SPRINT04-34](#sprint04-34) | Retorna 200 OK quando foi enviado o parâmetro "deliveryTime" do tipo caractere | `POST /order-and-go/v1/delivery` | Média |
| [SPRINT04-35](#sprint04-35) | Retorna 200 OK quando foi enviado o parâmetro "deliveryTime" vazio | `POST /order-and-go/v1/delivery` | Média |
| [SPRINT04-36](#sprint04-36) | Retorna 200 OK quando foi enviado o parâmetro "deliveryTime" removendo o parâmetro | `POST /order-and-go/v1/delivery` | Média |
| [SPRINT04-37](#sprint04-37) | Retorna 200 OK quando foi enviado o parâmetro "productsCount" removendo o parâmetro | `POST /order-and-go/v1/delivery` | Média |
| [SPRINT04-38](#sprint04-38) | Retorna 200 OK quando foi enviado o parâmetro "productsCount" vazio | `POST /order-and-go/v1/delivery` | Média |
| [SPRINT04-39](#sprint04-39) | Retorna 200 OK quando foi enviado o parâmetro "productsCount" do tipo caractere | `POST /order-and-go/v1/delivery` | Média |
| [SPRINT04-40](#sprint04-40) | Retorna 200 OK quando foi enviado o parâmetro "productsCount" do tipo string | `POST /order-and-go/v1/delivery` | Média |
| [SPRINT04-41](#sprint04-41) | Retorna 200 OK quando removido o Body | `POST /order-and-go/v1/delivery` | Média |

---

<a id="sprint04-1"></a>

## SPRINT04-1 — [POST /api/v1/kits/{id}/products] Retorna 500 Internal Server Error ao enviar requisição POST com parâmetro ID do tipo string.

- **Endpoint:** `POST /api/v1/kits/:id/products`
- **Prioridade:** Média

Passos para reproduzir:

1. Enviar requisição POST /api/v1/kits/{id}/products

```bash
curl --location 'https://cnt-a58bf336-1750-48d2-af13-66d2ef131de4.containerhub.tripleten-services.com/api/v1/kits/7/products' \
--header 'Content-Type: application/json' \
--data '{
  "productsList": [
    {
      "id": "teste",
      "quantity": 2
    }
  ]
}'
```

Resultado esperado: Deve retornar 400 Bad Request.

Resultado real: Retorna 500 Internal Server Error

**Evidências no Jira:** Captura de Tela 2026-06-14 às 13.30.58.png

---

<a id="sprint04-2"></a>

## SPRINT04-2 — [POST /api/v1/kits/{id}/products] Retorna 500 Internal Server Error ao enviar requisição POST com parâmetro ID vazio.

- **Endpoint:** `POST /api/v1/kits/:id/products`
- **Prioridade:** Média

Passos para reproduzir:

1. Enviar requisição POST /api/v1/kits/{id}/products

```bash
curl --location 'https://cnt-b352f8eb-9b13-4e6b-983b-a0d6dfc92479.containerhub.tripleten-services.com/api/v1/kits/7/products' \
--header 'Content-Type: application/json' \
--data '{
  "productsList": [
    {
      "id": "",
      "quantity": 1
    }
  ]
}'
```

Resultado esperado: Deve retornar 400 Bad Request.

Resultado real: Retorna 500 Internal Server Error.

**Evidências no Jira:** Captura de Tela 2026-06-14 às 15.54.45.png

---

<a id="sprint04-3"></a>

## SPRINT04-3 — [POST /api/v1/kits/{id}/products] Retorna 500 Internal Server Error ao enviar requisição POST com parâmetro ID do tipo null.

- **Endpoint:** `POST /api/v1/kits/:id/products`
- **Prioridade:** Média

Passos para reproduzir:

1. Enviar requisição POST /api/v1/kits/{id}/products

```bash
curl --location 'https://cnt-1d785c53-c034-4ba7-b365-f97e95198f21.containerhub.tripleten-services.com/api/v1/kits/7/products' \
--header 'Content-Type: application/json' \
--data '{
  "productsList": [
    {
      "id":"null"
      "quantity": 1
    }
  ]
}'
```

Resultado esperado: Deve retornar 400 Bad Request.

Resultado real: Retorna 500 Internal Server Error.

**Evidências no Jira:** Captura de Tela 2026-06-14 às 19.30.03.png

---

<a id="sprint04-4"></a>

## SPRINT04-4 — [POST /api/v1/kits/{id}/products] Retorna 500 Internal Server Error ao enviar requisição POST com parâmetro ID do tipo caractere especial.

- **Endpoint:** `POST /api/v1/kits/:id/products`
- **Prioridade:** Média

Passos para reproduzir:

1. Enviar requisição POST /api/v1/kits/{id}/products

```bash
curl --location 'https://cnt-1d785c53-c034-4ba7-b365-f97e95198f21.containerhub.tripleten-services.com/api/v1/kits/7/products' \
--header 'Content-Type: application/json' \
--data '{
  "productsList": [
    {
      "id":"###"
      "quantity": 1
    }
  ]
}'
```

Resultado esperado: Deve retornar 400 Bad Request.

Resultado real: Retorna 500 Internal Server Error.

**Evidências no Jira:** Captura de Tela 2026-06-14 às 19.38.21.png

---

<a id="sprint04-5"></a>

## SPRINT04-5 — [POST /api/v1/kits/{id}/products] Retorna 500 Internal Server Error ao enviar requisição POST com parâmetro ID muito longo.

- **Endpoint:** `POST /api/v1/kits/:id/products`
- **Prioridade:** Média

Passos para reproduzir:

1. Enviar requisição POST /api/v1/kits/{id}/products

```bash
curl --location 'https://cnt-1d785c53-c034-4ba7-b365-f97e95198f21.containerhub.tripleten-services.com/api/v1/kits/7/products' \
--header 'Content-Type: application/json' \
--data '{
  "productsList": [
    {
      "id":"2739484756589"
      "quantity": 1
    }
  ]
}'
```

Resultado esperado: Deve retornar 400 Bad Request.

Resultado real: Retorna 500 Internal Server Error.

**Evidências no Jira:** Captura de Tela 2026-06-14 às 19.43.22.png

---

<a id="sprint04-6"></a>

## SPRINT04-6 — [POST /api/v1/kits/{id}/products] Retorna 500 Internal Server Error ao enviar requisição POST com parâmetro ID do tipo negativo.

- **Endpoint:** `POST /api/v1/kits/:id/products`
- **Prioridade:** Média

Passos para reproduzir:

1. Enviar requisição POST /api/v1/kits/{id}/products

```bash
curl --location 'https://cnt-1d785c53-c034-4ba7-b365-f97e95198f21.containerhub.tripleten-services.com/api/v1/kits/7/products' \
--header 'Content-Type: application/json' \
--data '{
  "productsList": [
    {
      "id":-1
      "quantity": 1
    }
  ]
}'
```

Resultado esperado: Deve retornar 400 Bad Request.

Resultado real: Retorna 500 Internal Server Error.

**Evidências no Jira:** Captura de Tela 2026-06-14 às 19.50.51.png

---

<a id="sprint04-7"></a>

## SPRINT04-7 — [POST /api/v1/kits/{id}/products] Retorna 500 Internal Server Error ao enviar requisição POST com o "productsList" como um objeto.

- **Endpoint:** `POST /api/v1/kits/:id/products`
- **Prioridade:** Média

Passos para reproduzir:

1. Enviar requisição POST /api/v1/kits/{id}/products

```bash
curl --location 'https://cnt-8543dee6-95ed-49c7-9e05-5b2c5fd2db90.containerhub.tripleten-services.com/api/v1/kits/7/products' \
--header 'Content-Type: application/json' \
--data '{
  "productsList": {}
}'
```

Resultado esperado: Deve retornar 400 Bad Request.

Resultado real: Retorna 500 Internal Server Error.

**Evidências no Jira:** Captura de Tela 2026-06-14 às 20.55.14.png

---

<a id="sprint04-8"></a>

## SPRINT04-8 — [POST /api/v1/kits/{id}/products] Retorna 200 OK ao enviar requisição POST com o ID excluído.

- **Endpoint:** `POST /api/v1/kits/:id/products`
- **Prioridade:** Média

Passos para reproduzir:

1. Enviar requisição POST /api/v1/kits/{id}/products

```bash
curl --location 'https://cnt-8543dee6-95ed-49c7-9e05-5b2c5fd2db90.containerhub.tripleten-services.com/api/v1/kits/7/products' \
--header 'Content-Type: application/json' \
--data '{
  "productsList": [
    {
  
      "quantity": 1
    }
  ]
}'
```

Resultado esperado: Deve retornar 400 Bad Request.

Resultado real: Retorna 200 OK.

**Evidências no Jira:** Captura de Tela 2026-06-14 às 21.03.23.png

---

<a id="sprint04-9"></a>

## SPRINT04-9 — [POST /api/v1/kits/{id}/products] Retorna 200 OK ao enviar requisição POST removendo o Body por completo.

- **Endpoint:** `POST /api/v1/kits/:id/products`
- **Prioridade:** Média

Passos para reproduzir:

1. Enviar requisição POST /api/v1/kits/{id}/products

```bash
curl --location --request POST 'https://cnt-8543dee6-95ed-49c7-9e05-5b2c5fd2db90.containerhub.tripleten-services.com/api/v1/kits/7/products' \
--header 'Content-Type: application/json' \
--data ''
```

Resultado esperado: Deve retornar 400 Bad Request.

Resultado real: Retorna 200 OK.

**Evidências no Jira:** Captura de Tela 2026-06-14 às 21.08.24.png

---

<a id="sprint04-10"></a>

## SPRINT04-10 — [POST /api/v1/kits/{id}/products] Retorna 200 OK ao enviar requisição POST com o "productsList"vazio.

- **Endpoint:** `POST /api/v1/kits/:id/products`
- **Prioridade:** Média

Passos para reproduzir:

1. Enviar requisição POST /api/v1/kits/{id}/products

```bash
curl --location 'https://cnt-8543dee6-95ed-49c7-9e05-5b2c5fd2db90.containerhub.tripleten-services.com/api/v1/kits/7/products' \
--header 'Content-Type: application/json' \
--data ' {
  "productsList": [ ]
}'
```

Resultado esperado: Deve retornar 400 Bad Request.

Resultado real: Retorna 200 OK.

**Evidências no Jira:** Captura de Tela 2026-06-14 às 21.15.09.png

---

<a id="sprint04-11"></a>

## SPRINT04-11 — [POST /api/v1/kits/{id}/products] Retorna 500 Internal Server Error ao enviar requisição POST com o "quantity" do tipo string.

- **Endpoint:** `POST /api/v1/kits/:id/products`
- **Prioridade:** Média

_Descrição não preenchida no Jira._

**Evidências no Jira:** Captura de Tela 2026-06-15 às 23.23.09.png

---

<a id="sprint04-12"></a>

## SPRINT04-12 — [POST /api/v1/kits/{id}/products] Retorna 200 OK ao enviar requisição POST com o "quantity" vazio.

- **Endpoint:** `POST /api/v1/kits/:id/products`
- **Prioridade:** Média

Passos para reproduzir:

1. Enviar requisição POST /api/v1/kits/{id}/products

```bash
curl --location 'https://cnt-d8f8422a-4111-4751-9510-1bb15c5f5a12.containerhub.tripleten-services.com/api/v1/kits/7/products' \
--header 'Content-Type: application/json' \
--data ' {
  "productsList": [
    {
      "id": 0,
      "quantity":""
      
    }
  ]
}'
```

Resultado esperado: Deve retornar 400 Bad Request.

Resultado real: Retorna 200 OK.

**Evidências no Jira:** Captura de Tela 2026-06-15 às 23.33.23.png

---

<a id="sprint04-13"></a>

## SPRINT04-13 — [POST /api/v1/kits/{id}/products] Retorna 500 Internal Server Error ao enviar requisição POST com o "quantity" do tipo null.

- **Endpoint:** `POST /api/v1/kits/:id/products`
- **Prioridade:** Média

Passos para reproduzir:

1. Enviar requisição POST /api/v1/kits/{id}/products

```bash
curl --location 'https://cnt-d8f8422a-4111-4751-9510-1bb15c5f5a12.containerhub.tripleten-services.com/api/v1/kits/7/products' \
--header 'Content-Type: application/json' \
--data ' {
  "productsList": [
    {
      "id": 0,
      "quantity":"null"
      
    }
  ]
}'
```

Resultado esperado: Deve retornar 400 Bad Request.

Resultado real: Retorna 500 Internal Server Error.

**Evidências no Jira:** Captura de Tela 2026-06-15 às 23.42.46.png

---

<a id="sprint04-14"></a>

## SPRINT04-14 — [POST /api/v1/kits/{id}/products] Retorna 500 Internal Server Error ao enviar requisição POST com o "quantity" do tipo caractere especial.

- **Endpoint:** `POST /api/v1/kits/:id/products`
- **Prioridade:** Média

Passos para reproduzir:

1. Enviar requisição POST /api/v1/kits/{id}/products

```bash
curl --location 'https://cnt-d8f8422a-4111-4751-9510-1bb15c5f5a12.containerhub.tripleten-services.com/api/v1/kits/7/products' \
--header 'Content-Type: application/json' \
--data ' {
  "productsList": [
    {
      "id": 0,
      "quantity":"&&&"
      
    }
  ]
}'
```

Resultado esperado: Deve retornar 400 Bad Request.

Resultado real: Retorna 500 Internal Server Error.

**Evidências no Jira:** Captura de Tela 2026-06-15 às 23.51.05.png

---

<a id="sprint04-15"></a>

## SPRINT04-15 — [POST /api/v1/kits/{id}/products] Retorna 500 Internal Server Error ao enviar requisição POST com o "quantity" do tipo muito longo.

- **Endpoint:** `POST /api/v1/kits/:id/products`
- **Prioridade:** Média

Passos para reproduzir:

1. Enviar requisição POST /api/v1/kits/{id}/products

```bash
curl --location 'https://cnt-d8f8422a-4111-4751-9510-1bb15c5f5a12.containerhub.tripleten-services.com/api/v1/kits/7/products' \
--header 'Content-Type: application/json' \
--data ' {
  "productsList": [
    {
      "id": 0,
      "quantity":"38475668675"
      
    }
  ]
}'
```

Resultado esperado: Deve retornar 400 Bad Request.

Resultado real: Retorna 500 Internal Server Error.

**Evidências no Jira:** Captura de Tela 2026-06-15 às 23.56.17.png

---

<a id="sprint04-16"></a>

## SPRINT04-16 — [POST /api/v1/kits/{id}/products] Retorna 200 OK ao enviar requisição POST com o "quantity" do tipo negativo.

- **Endpoint:** `POST /api/v1/kits/:id/products`
- **Prioridade:** Média

Passos para reproduzir:

1. Enviar requisição POST /api/v1/kits/{id}/products

```bash
curl --location 'https://cnt-788e8f85-4e18-40d4-a377-8c8be9ef8943.containerhub.tripleten-services.com/api/v1/kits/7/products' \
--header 'Content-Type: application/json' \
--data ' {
  "productsList": [
    {
      "id": 0,
      "quantity":-1
      
    }
  ]
}'
```

Resultado esperado: Deve retornar 400 Bad Request.

Resultado real: Retorna 200 OK.

**Evidências no Jira:** Captura de Tela 2026-06-16 às 00.05.26.png

---

<a id="sprint04-17"></a>

## SPRINT04-17 — [POST /api/v1/kits/{id}/products] Retorna 500 Internal Server Error ao enviar requisição POST com o "quantity" excluído.

- **Endpoint:** `POST /api/v1/kits/:id/products`
- **Prioridade:** Média

Passos para reproduzir:

1. Enviar requisição POST /api/v1/kits/{id}/products

```bash
curl --location 'https://cnt-788e8f85-4e18-40d4-a377-8c8be9ef8943.containerhub.tripleten-services.com/api/v1/kits/7/products' \
--header 'Content-Type: application/json' \
--data ' {
  "productsList": [
    {
      "id": 0
      
    }
  ]
}'
```

Resultado esperado: Deve retornar 400 Bad Request.

Resultado real: Retorna 500 Internal Server Error.

**Evidências no Jira:** Captura de Tela 2026-06-16 às 00.12.34.png

---

<a id="sprint04-18"></a>

## SPRINT04-18 — [POST /api/v1/kits/{id}/products] Retorna 500 Internal Server Error ao enviar requisição POST criando outro ID de kit da URL com uma string.

- **Endpoint:** `POST /api/v1/kits/:id/products`
- **Prioridade:** Média

Passos para reproduzir:

1. Enviar requisição POST /api/v1/kits/{id}/products

```bash
curl --location 'https://cnt-a2f7dddb-c2b8-4fe0-8094-839fa664a17c.containerhub.tripleten-services.com/api/v1/kits/a/products' \
--header 'Content-Type: application/json' \
--data ' {
  "productsList": [
    {
      "id": 1,
      "quantity": 1
    }
  ]
}'
```

Resultado esperado: Deve retornar 400 Bad Request.

Resultado real: Retorna 500 Internal Server Error.

****

**Evidências no Jira:** Captura de Tela 2026-06-16 às 11.11.17.png

---

<a id="sprint04-19"></a>

## SPRINT04-19 — [POST /api/v1/kits/{id}/products] Retorna 500 Internal Server Error ao enviar requisição POST criando outro ID de kit da URL com caractere especial.

- **Endpoint:** `POST /api/v1/kits/:id/products`
- **Prioridade:** Média

Passos para reproduzir:

1. Enviar requisição POST /api/v1/kits/{id}/products

```bash
curl --location 'https://cnt-a2f7dddb-c2b8-4fe0-8094-839fa664a17c.containerhub.tripleten-services.com/api/v1/kits/@/products' \
--header 'Content-Type: application/json' \
--data ' {
  "productsList": [
    {
      "id": 1,
      "quantity": 1
    }
  ]
}'
```

Resultado esperado: Deve retornar 400 Bad Request.

Resultado real: Retorna 500 Internal Server Error.

**Evidências no Jira:** Captura de Tela 2026-06-16 às 11.19.14.png

---

<a id="sprint04-20"></a>

## SPRINT04-20 — [POST /order-and-go/v1/delivery] Retorna o parâmetro "isItPossibleToDeliver": true ao enviar requisição POST com o parâmetro "deliveryTime": 7

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location 'https://cnt-3a1739ff-febe-4a75-9cc8-de8e6c8760ae.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--header 'Content-Type: application/json' \
--data '{
    "deliveryTime": 7,
    "productsCount": 1,
    "productsWeight": 1
}'
```

Resultado esperado:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": false,
    "hostDeliveryCost": 3,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 0
}
```

Resultado Real:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 3,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 5
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 11.44.03.png

---

<a id="sprint04-21"></a>

## SPRINT04-21 — [POST /order-and-go/v1/delivery] Retorna o parâmetro "isItPossibleToDeliver": true ao enviar requisição POST com o parâmetro "deliveryTime": 23

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location 'https://cnt-3a1739ff-febe-4a75-9cc8-de8e6c8760ae.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--header 'Content-Type: application/json' \
--data '{
    "deliveryTime": 23,
    "productsCount": 1,
    "productsWeight": 1
}'
```

Resultado esperado:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver":false,
    "hostDeliveryCost": 3,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost":0
}
```

Resultado Real:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 3,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 5
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 12.05.29.png

---

<a id="sprint04-22"></a>

## SPRINT04-22 — [POST /order-and-go/v1/delivery] Retorna 200 OK quando foi enviado o parâmetro "productsCount": -1

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location 'https://cnt-47a9c04e-a15c-48f8-a1ed-97009d67e751.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--header 'Content-Type: application/json' \
--data '{
    "deliveryTime": 8,
    "productsCount": -1,
    "productsWeight": 1
}'
```

Resultado esperado:

400 Bad Request

Resultado Real:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 3,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 0
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 15.29.29.png

---

<a id="sprint04-23"></a>

## SPRINT04-23 — [POST /order-and-go/v1/delivery] Retorna 200 OK quando foi enviado o parâmetro "productsCount" igual a 0.

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location 'https://cnt-47a9c04e-a15c-48f8-a1ed-97009d67e751.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--header 'Content-Type: application/json' \
--data '{
    "deliveryTime": 8,
    "productsCount": 0,
    "productsWeight": 1
}'
```

Resultado esperado:

400 Bad Request

Resultado Real:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 3,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 0
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 15.37.09.png

---

<a id="sprint04-24"></a>

## SPRINT04-24 — [POST /order-and-go/v1/delivery] Retorna 200 OK quando foi enviado o parâmetro "productsCount" igual a 16

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location 'https://cnt-47a9c04e-a15c-48f8-a1ed-97009d67e751.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--header 'Content-Type: application/json' \
--data '{
    "deliveryTime": 8,
    "productsCount": 16,
    "productsWeight": 1
}'
```

Resultado esperado:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 5,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 9
}
```

Resultado Real:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 5,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 5
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 16.03.48.png

---

<a id="sprint04-25"></a>

## SPRINT04-25 — [POST /order-and-go/v1/delivery] Retorna 200 OK quando foi enviado o parâmetro "productsWeight" é igual a -1

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location 'https://cnt-47a9c04e-a15c-48f8-a1ed-97009d67e751.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--header 'Content-Type: application/json' \
--data '{
    "deliveryTime": 8,
    "productsCount": 1,
    "productsWeight": -1
}'
```

Resultado esperado:

400 Bad Request

Resultado Real:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 3,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 0
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 16.14.11.png

---

<a id="sprint04-26"></a>

## SPRINT04-26 — [POST /order-and-go/v1/delivery] Retorna 200 OK quando foi enviado o parâmetro "productsWeight" é igual a 0

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location 'https://cnt-a1974ebb-9c68-474b-b85e-dd7b595c7d4a.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--header 'Content-Type: application/json' \
--data '{
    "deliveryTime": 8,
    "productsCount": 1,
    "productsWeight": 0
}'
```

Resultado esperado:

400 Bad Request

Resultado Real:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 3,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 0
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 16.21.40.png

---

<a id="sprint04-27"></a>

## SPRINT04-27 — [POST /order-and-go/v1/delivery] Retorna 200 OK quando foi enviado o parâmetro "productsWeight" é igual a 3.1

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location 'https://cnt-a1974ebb-9c68-474b-b85e-dd7b595c7d4a.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--header 'Content-Type: application/json' \
--data '{
    "deliveryTime": 8,
    "productsCount": 1,
    "productsWeight": 3.1
}'
```

Resultado esperado:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 5
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 0
}
```

Resultado Real:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 3,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 0
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 16.35.42.png

---

<a id="sprint04-28"></a>

## SPRINT04-28 — [POST /order-and-go/v1/delivery] Retorna 200 OK quando foi enviado o parâmetro "productsWeight" é igual a 6.1

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location 'https://cnt-a1974ebb-9c68-474b-b85e-dd7b595c7d4a.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--header 'Content-Type: application/json' \
--data '{
    "deliveryTime": 8,
    "productsCount": 1,
    "productsWeight": 6.1
}'
```

Resultado esperado:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 5,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 9
}
```

Resultado Real:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 5,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 0
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 16.48.17.png

---

<a id="sprint04-29"></a>

## SPRINT04-29 — [POST /order-and-go/v1/delivery] Retorna 200 OK quando foi enviado o parâmetro "productsWeight" do tipo null

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location 'https://cnt-46a8afbc-94d0-451a-9fc0-d62bb52526ea.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--header 'Content-Type: application/json' \
--data '{
    "deliveryTime": 8,
    "productsCount": 1,
    "productsWeight": null
}'
```

Resultado esperado:

400 Bad Request

Resultado Real:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 3,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 0
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 19.58.04.png

---

<a id="sprint04-30"></a>

## SPRINT04-30 — [POST /order-and-go/v1/delivery] Retorna 200 OK quando foi enviado o parâmetro "productsWeight" do tipo string

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location 'https://cnt-46a8afbc-94d0-451a-9fc0-d62bb52526ea.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--header 'Content-Type: application/json' \
--data '{
    "deliveryTime": 8,
    "productsCount": 1,
    "productsWeight": "teste"
}'
```

Resultado esperado:

400 Bad Request

Resultado Real:

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 3,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 0
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 20.03.24.png

---

<a id="sprint04-31"></a>

## SPRINT04-31 — [POST /order-and-go/v1/delivery] Retorna 200 OK quando foi enviado o parâmetro "productsWeight" do tipo caractere

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location 'https://cnt-46a8afbc-94d0-451a-9fc0-d62bb52526ea.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--header 'Content-Type: application/json' \
--data-raw '{
    "deliveryTime": 8,
    "productsCount": 1,
    "productsWeight": "@@@"
}'
```

Resultado esperado:

400 Bad Request

Resultado Real:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 3,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 0
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 20.16.44.png

---

<a id="sprint04-32"></a>

## SPRINT04-32 — [POST /order-and-go/v1/delivery] Retorna 200 OK quando foi enviado o parâmetro "productsWeight" vazio

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location 'https://cnt-46a8afbc-94d0-451a-9fc0-d62bb52526ea.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--header 'Content-Type: application/json' \
--data '{
    "deliveryTime": 8,
    "productsCount": 1,
    "productsWeight": ""
}'
```

Resultado esperado:

400 Bad Request

Resultado Real:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 3,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 0
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 20.21.42.png

---

<a id="sprint04-33"></a>

## SPRINT04-33 — [POST /order-and-go/v1/delivery] Retorna 200 OK quando foi enviado o parâmetro "deliveryTime" como uma string

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location 'https://cnt-46a8afbc-94d0-451a-9fc0-d62bb52526ea.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--header 'Content-Type: application/json' \
--data '{
    "deliveryTime": "teste",
    "productsCount": 1,
    "productsWeight": 6
}'
```

Resultado esperado:

400 Bad Request

Resultado Real:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 5,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 0
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 20.52.25.png

---

<a id="sprint04-34"></a>

## SPRINT04-34 — [POST /order-and-go/v1/delivery] Retorna 200 OK quando foi enviado o parâmetro "deliveryTime" do tipo caractere

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location 'https://cnt-a1fa7f22-7593-4ddb-a25b-265c3918ed71.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--header 'Content-Type: application/json' \
--data-raw '{
    "deliveryTime": "@@@",
    "productsCount": 1,
    "productsWeight": 6
}'
```

Resultado esperado:

400 Bad Request

Resultado Real:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 5,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 0
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 20.58.57.png

---

<a id="sprint04-35"></a>

## SPRINT04-35 — [POST /order-and-go/v1/delivery] Retorna 200 OK quando foi enviado o parâmetro "deliveryTime" vazio

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location 'https://cnt-a1fa7f22-7593-4ddb-a25b-265c3918ed71.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--header 'Content-Type: application/json' \
--data '{
    "deliveryTime": "",
    "productsCount": 1,
    "productsWeight": 6
}'
```

Resultado esperado:

400 Bad Request

Resultado Real:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 5,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 5
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 21.05.02.png

---

<a id="sprint04-36"></a>

## SPRINT04-36 — [POST /order-and-go/v1/delivery] Retorna 200 OK quando foi enviado o parâmetro "deliveryTime" removendo o parâmetro

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location 'https://cnt-a1fa7f22-7593-4ddb-a25b-265c3918ed71.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--header 'Content-Type: application/json' \
--data '{

    "productsCount": 1,
    "productsWeight": 6
}'
```

Resultado esperado:

400 Bad Request

Resultado Real:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 5,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 0
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 21.10.12.png

---

<a id="sprint04-37"></a>

## SPRINT04-37 — [POST /order-and-go/v1/delivery] Retorna 200 OK quando foi enviado o parâmetro "productsCount" removendo o parâmetro

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location 'https://cnt-a1fa7f22-7593-4ddb-a25b-265c3918ed71.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--header 'Content-Type: application/json' \
--data '{
    "deliveryTime": 1,

    "productsWeight": 6
}'
```

Resultado esperado:

400 Bad Request

Resultado Real:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 3,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 5
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 21.19.17.png

---

<a id="sprint04-38"></a>

## SPRINT04-38 — [POST /order-and-go/v1/delivery] Retorna 200 OK quando foi enviado o parâmetro "productsCount" vazio

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location 'https://cnt-a1fa7f22-7593-4ddb-a25b-265c3918ed71.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--header 'Content-Type: application/json' \
--data '{
    "deliveryTime": 8,
    "productsCount": "",
    "productsWeight": 6
}'
```

Resultado esperado:

400 Bad Request

Resultado Real:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 5,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 0
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 21.24.39.png

---

<a id="sprint04-39"></a>

## SPRINT04-39 — [POST /order-and-go/v1/delivery] Retorna 200 OK quando foi enviado o parâmetro "productsCount" do tipo caractere

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location 'https://cnt-a1fa7f22-7593-4ddb-a25b-265c3918ed71.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--header 'Content-Type: application/json' \
--data-raw '{
    "deliveryTime": 8,
    "productsCount": "@@@",
    "productsWeight": 6
}'
```

Resultado esperado:

400 Bad Request

Resultado Real:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 3,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 0
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 21.37.11.png

---

<a id="sprint04-40"></a>

## SPRINT04-40 — [POST /order-and-go/v1/delivery] Retorna 200 OK quando foi enviado o parâmetro "productsCount" do tipo string

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location 'https://cnt-a1fa7f22-7593-4ddb-a25b-265c3918ed71.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--header 'Content-Type: application/json' \
--data '{
    "deliveryTime": 8,
    "productsCount": "teste",
    "productsWeight": 6
}'
```

Resultado esperado:

400 Bad Request

Resultado Real:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 3,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 0
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 21.41.37.png

---

<a id="sprint04-41"></a>

## SPRINT04-41 — [POST /order-and-go/v1/delivery] Retorna 200 OK quando removido o Body

- **Endpoint:** `POST /order-and-go/v1/delivery`
- **Prioridade:** Média

Passos para reproduzir:

```bash
curl --location --request POST 'https://cnt-a1fa7f22-7593-4ddb-a25b-265c3918ed71.containerhub.tripleten-services.com/order-and-go/v1/delivery' \
--data ''
```

Resultado esperado:

400 Bad Request

Resultado Real:

200 OK

```json
{
    "name": "Order and Go",
    "isItPossibleToDeliver": true,
    "hostDeliveryCost": 3,
    "toBeDeliveredTime": {
        "min": 20,
        "max": 25
    },
    "clientDeliveryCost": 0
}
```

**Evidências no Jira:** Captura de Tela 2026-06-17 às 21.48.00.png

---
