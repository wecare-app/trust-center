---
sidebar_position: 6
---

# Desligar colaborador

Utilize esse método para desligar colaboradores na plataforma.

Esse método desliga os colaboradores, podendo ser de forma imediata ou programada. Essa ação só é reversível pela plataforma.

:::info[Disponibilidade da funcionalidade]
O agendamento do desligamento está disponível, no momento, apenas para o ambiente de Homologação da WeCare.
Para ambientes produtivos da WeCare, não informar os campos adicionais no corpo da requisição.
:::

## Método

**DELETE**
`api/v2/users/:key`

## Headers

| Header        | Valor               |
| ------------- | ------------------- |
| Authorization | Bearer access_token |

Obtenha o `access_token` pelo [método de autenticação](/api/autenticacao).

## Atributos

### Obrigatórios

| Atributos          | Tipo   | Descrição                                                   |
| ------------------ | ------ | ----------------------------------------------------------- |
| key                | string | Chave do colaborador usada no cadastro (email ou matrícula) |
| schedule_date      | date   | Data de desligamento no formato DD/MM/YYYY                  |
| external_reference | string | Referência externa ao seu sistema                           |


## Requisição

```json
{
  "schedule_date": "25/11/2025",
  "external_reference": "REQ-001"
}
```

:::warning[Atenção]
Caso a data de desligamento não seja informada, a plataforma desligará imediamente o colaborador.
:::

## Resposta

### 200

```json
{
  "message": "Colaborador Diego Oliveira dos Santos desligado(a)"
}
```

### 401

```json
{
  "error": "access token expired"
}
```

Nesse caso, verifique se o `access_token` no header `Authorization` está correto.

### 404

```json
{
  "error": "user not found"
}
```

Nesse caso, não existe colaborador para a chave informada.

## Funcionamento do agendamento

A WeCare realizará os desligamentos, por padrão, às 00:00 do dia de agendamento. Esse horário pode ser modificado para sua empresa, entre em contato com a equipe de TI por meio do email: [ti@sejawecare.com.br](mailto:ti@sejawecare.com.br)

Caso o desligamento falhe, enviaremos uma notificação por email aos responsáveis da empresa e também conseguimos configurar o envio de uma notificação para o seu sistema, no formato de webhook.

### Cancelar o agendamento

Caso deseje cancelar o agendamento realizado, consulte os agendamentos feitos usando o endpoint:

**GET**
`api/v2/scheduled_changes`

Para cancelar um agendamento, utilize o endpoint:

**DELETE**
`api/v2/scheduled_changes/:uuid/cancel`

| Atributos | Tipo   | Descrição                                                   |
| --------- | ------ | ----------------------------------------------------------- |
| uuid      | string | Identificador do agendamento de alteração                   |
