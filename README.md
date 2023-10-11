# DailyReminder

Uma API para controle de atividades diárias.

---

## Endpoints

- Atividade 
    - [Cadastrar](#cadastrar-atividade)
    - [Mostrar Detalhes](#detalhar-atividade)
    - [Atualizar](#atualizar-atividade)
    - [Deletar](#deletar-atividade)
    - [Mostrar Todos](#detalhar-todas-atividades)
- Lembrete
    - [Cadastrar](#cadastrar-lembrete)
    - [Mostrar Detalhes](#detalhar-lembrete)
    - [Atualizar](#atualizar-lembrete)
    - [Deletar](#deletar-lembrete)
    - [Mostrar Todos](#detalhar-todos-lembretes)

---

## Cadastrar Atividade

`POST` /api/atividades


**Campos de Requisição**

| Campo | Tipo | Obrigatório | Descrição |
|-------|------|:-------------:|-----------|
| atividade_id | int | Sim | O código da atividade feita. |
| atividade | texto | Sim | Um nome para uma atividade a ser realizada de no máximo 50 caracteres. |
| data | Data | Sim | A data da atividade. |
| duracao | DateTime | Não | A duração do tempo da atividade. |
| lembretes | String | Sim | Lembrete que já está cadastrado |


**Exemplo de Corpo de Requisição**

```js
{
    "id": 9,
    "duracao": 60,
    "dataDia": "2023-10-11",
    "atividade": "Estudar",
    "created_at": "2023-10-11",
    "lembrete": {
        "id": 1,
        "mensagem": "Jogar GTA",
        "duracao": 60
        }
}
```

**Código de Resposta**

| Código | Descrição |
| - | - |
| 201 | Despesa criada com sucesso. | 
| 400 | Os campos enviados são inválidos. |

---

## Detalhar Atividade

`GET` /api/atividades/{id}

**Exemplo de Corpo de Requisição**

```js
{

    "id": 9,
    "duracao": 60,
    "dataDia": "2023-10-11",
    "atividade": "Estudar",
    "created_at": "2023-10-11",
    "lembrete": {
        "id": 1,
        "mensagem": "Jogar GTA",
        "duracao": 60
        }

    ]
}
```

**Código de Resposta**

| Código | Descrição |
| - | - |
| 200 | Dados retornados com sucesso. |
| 204 | Sem conteúdo. |
| 404 | Não existe despesa com o id informado. |

---

## Atualizar Atividade

`PATCH` /api/atividades/{id}

**Exemplo de Corpo de Requisição**

```js
{
    atividade_id: 2,
    atividade: 'Estudar',
    dia: '2023-03-04',
    duracao: 02:30:00,
    semana_atividade: [
        'terça-feira',
        'quarta-feira',
        'quinta-feira',
    ]
}
```

**Código de Resposta**

| Código | Descrição |
| - | - |
| 201 | Dado atualizado com sucesso. | 
| 404 | Não existe despesa com o id informado. |
| 406 | Dado inválido ou errado. |

## Deletar Atividade

`DELETE` /api/atividades/{id}

**Código de Resposta**

| Código | Descrição |
| - | - |
| 200 | Dado deletado com sucesso. | 
| 404 | Não existe despesa com o id informado. |


## Detalhar Todas Atividades

`GET` /api/x/

**Exemplo de Corpo de Requisição**

```js
{
    [
        {
            atividade_id: 1,
            atividade: 'Treinar',
            dia: '2023-03-04',
            duracao: 01:30:00,
            semana_atividade: [
                'segunda-feira',
                'terça-feira',
                'quarta-feira',
                'quinta-feira',
                'sexta-feira',
            ]
        },
        {
            atividade_id: 2,
            atividade: 'Estudar',
            dia: '2023-03-04',
            duracao: 02:30:00,
            semana_atividade: [
                'terça-feira',
                'quarta-feira',
                'quinta-feira',
            ] 
        }
    ]
}
```

**Código de Resposta**

| Código | Descrição |
| - | - |
| 200 | Dados retornados com sucesso. | 
| 204 | Sem conteúdo. |
| 400 | Má Requisição ou probida. |
| 404 | Não existe despesa com o id informado. |

---

## Cadastrar Lembrete

`POST` /api/x


**Campos de Requisição**

| Campo | Tipo | Obrigatório | Descrição |
|-------|------|:-------------:|-----------|
| data_id | int | Sim | O código do dia. | 
| data | Data | Sim | Uma data escolhida pelo usuário. |

**Exemplo de Corpo de Requisição**

```js
{
        "id": 1,
        "mensagem": "Jogar GTA",
        "duracao": 60
}
```

**Código de Resposta**

| Código | Descrição |
| - | - |
| 201 | Despesa criada com sucesso. | 
| 400 | Os campos enviados são inválidos. |

---

## Detalhar Lembrete

`GET` /api/x/{id}

**Exemplo de Corpo de Requisição**

```js
{
        "id": 1,
        "mensagem": "Jogar GTA",
        "duracao": 60
}
```

**Código de Resposta**

| Código | Descrição |
| - | - |
| 200 | Dados retornados com sucesso. |
| 204 | Sem conteúdo. |
| 404 | Não existe despesa com o id informado. |

---

## Atualizar Lembrete

`PATCH` /api/x/{id}

**Exemplo de Corpo de Requisição**

```js
{
        "id": 1,
        "mensagem": "Jogar GTA",
        "duracao": 60
}
```

**Código de Resposta**

| Código | Descrição |
| - | - |
| 201 | Dado atualizado com sucesso. | 
| 404 | Não existe despesa com o id informado. |
| 406 | Dado inválido ou errado. |

## Deletar Lembrete

`DELETE` /api/x/{id}

**Código de Resposta**

| Código | Descrição |
| - | - |
| 200 | Dado deletado com sucesso. | 
| 404 | Não existe despesa com o id informado. |


## Detalhar Todos Lembretes

`GET` /api/x/

**Exemplo de Corpo de Requisição**

```js
{
    [
        {
            "id": 1,
            "mensagem": "Jogar GTA",
            "duracao": 60
        },
        {
            "id": 1,
            "mensagem": "Jogar GTA",
            "duracao": 60
        },
    ]
}
```

**Código de Resposta**

| Código | Descrição |
| - | - |
| 200 | Dados retornados com sucesso. | 
| 204 | Sem conteúdo. |
| 400 | Má Requisição ou probida. |
| 404 | Não existe despesa com o id informado. |

---
