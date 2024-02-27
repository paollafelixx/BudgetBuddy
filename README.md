# BudgetBuddy
API Rest do projeto Budget Buddy - Controle de gastos pessoas - Turma Z


## Requisitos

- [ ] CRUD de Categorias 
- [ ] CRUD de Movimentações
- [ ] CRUD de Usuarios
- [ ] Autenticação
- [ ] Dashboard

## Documentação do API

### Endpoints

- [Listar Categorias](#listar-categorias)
- [Apagar Categoria](#apagar-categoria)
- [Detalhar Categoria](#detalhar-categoria)
- [Cadastrar Categoria](#cadastrar-cactegorias)
- [Atualizar Categoria](#atualizar-categoria)

### Listar Categorias

`GET` /categoria

Retorna um array com todas as categorias cadastradas pelo usuario atual.

##### Exemplo de Respostas

```js
[
    {
        "id": 1,
        "nome":"Alimentação",
        "icone":"fast-food"
    }
]
```

#### Códigos de Resposta

| código | descrição |
|--------|-----------|
|200| Categorias retornadas com sucesso
|401| Não autorizado. Realize a autenticação em /login

---

### Cadastrar Categoria

`POST` /categoria

Cadastra uma categoria com os dados enviados no corpo da requisição.

#### Corpo de Requisição

| campo | tipo | obrigatório | descrição
|-------|------|:-------------:|----------
| nome  | string| ✅ | Um nome curto para identificar a cateoria
| icone | string| ❌ | O nome do ícone conforme bibilioteca Material Icons 

```js
{
    "nome": "Alimentação",
    "icone: "fast-food"
}
```

##### Exemplo de Respostas

```js
[
    {
        "id": 1,
        "nome":"Alimentação",
        "icone":"fast-food"
    }
]
```

#### Código de Resposta

| código | descrição |
|--------|-----------|
|201| Categoria cadastrada com sucesso
|400| Validação falhou. Verifique os dados enviados no corpo da aquisição
|401| Não autorizado. Realize a autenticação em /login

---

### Apagar categoria

`DELETE` /categoria/`{id}`

Apaga a categoria com o `id` informado no parâmetro de path.

#### Código de Resposta

| código | descrição |
|--------|-----------|
|204| Categoria apagada com sucesso
|401| Não autorizado. Realize a autenticação em /login

---
### Detalhar Categoria

`GET` /CATEGORIA/`{id}`

Retorna os dados da categoria com o `id` informado no parâmetro de path.

##### Exemplo de Respostas

```js
// requisição / categoria /1
[
    {
        "id": 1,
        "nome":"Alimentação",
        "icone":"fast-food"
    }
]
```

#### Código de Resposta

| código | descrição |
|--------|-----------|
|200| Categoria retornada com sucesso
|401| Não autorizado. Realize a autenticação em /login
|404| Não existe categoria com o `id` informado

---

### Atualizar Categoria

`PUT` /categoria/`{id}`

Atualiza os daos da categoria com o `id` informado no path

#### Corpo de Requisição

| campo | tipo | obrigatório | descrição
|-------|------|:-------------:|----------
| nome  | string| ✅ | Um nome curto para identificar a cateoria
| icone | string| ✅ | O nome do ícone conforme bibilioteca Material Icons 

```js
{
    "nome": "Alimentação",
    "icone: "fast-food"
}
```

##### Exemplo de Respostas

```js
[
    {
        "id": 1,
        "nome":"Alimentação",
        "icone":"fast-food"
    }
]
```

#### Código de Resposta

| código | descrição |
|--------|-----------|
|200| Categoria cadastrada com sucesso
|400| Validação falhou. Verifique os dados enviados no corpo da requisição
|401| Não autorizado. Realize a autenticação em /login
|404| Não existe categoria com o `id` informado

---
