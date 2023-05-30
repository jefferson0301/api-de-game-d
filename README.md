# API DE GAMES
Esta  api é utliizada para lore ipsun
##Endpoints
### GET /games
Esse endpoint é responsável por mostrar todos os games disponíveis no banco de dados.
#### Parametros
Nenhum
#### Respostas
##### OK 200
Caso essa resposta aconteça você vai receber a listagem de todos os games.
Exemplo de resposta:
```
[
    {
        "id": 23,
        "title": "Call of Duty",
        "year": 2019,
        "price": 60
    },
    {
        "id": 65,
        "title": "Sea of thieves",
        "year": 2018,
        "price": 40
    },
    {
        "id": 2,
        "title": "Minecraft",
        "year": 2012,
        "price": 20
    }
]
```

##### Falha na autenticação 401
Caso essa resposta aconteça significa que houve alguma falha no processo de requisição
Motivos: Token inválido, Token expirado.
Exemplo de resposta:
```
{
    "err": "Token Inválido"
}
```

### POST /auth
Esse endpoint é responsável por fazer o processo de login
#### Parametros
email: Email do usuário cadastrado no sistema. Com aquele determinado email.

password: Senha do usuário cadastrado no sistema 
Exemplo:
```
{
        "email": "teste@teste.com",     
        "password": 123
}
```
#### Respostas
##### OK 200
Caso essa resposta aconteça você vai receber o token JWT para acessar enpoints protegidos na API.
Exemplo de resposta:
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJ0ZXN0ZUB0ZXN0ZS5jb20iLCJpYXQiOjE2ODU0NTQyNzQsImV4cCI6MTY4NTYyNzA3NH0.5mi9QWZWmWJvYV6haYVh7htpQSm-CytM5okXNxDpywA"
}
```

##### Falha na autenticação 401
Caso essa resposta aconteça significa que houve alguma falha no processo de requisição
Motivos: senha ou email incorretos.
Exemplo de resposta:
```
{
err: "Credenciais inválidas!"
}
```
