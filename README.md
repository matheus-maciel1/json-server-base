Documentação JSON server base API
==================================

URL BASE: https://reciclatonapi.herokuapp.com/

-----------------------------------------------------------------
### !! --> PERMISSÕES SEM LOGIN <-- !!

## Lista de usuários:
GET: 
    https://reciclatonapi.herokuapp.com/664/users

------------------------------------

## Usuário único: 
GET:
    https://reciclatonapi.herokuapp.com/664/users/${id}

------------------------------------

## Para logar:
POST:
    https://reciclatonapi.herokuapp.com/login

        Exemplo de conteúdo:
            {
                "email": "julinho@gmail.com",
                "password": "123456"
            }

-------------------------------------

## Cadastrar usuário:
POST:
    https://reciclatonapi.herokuapp.com/register

        Exemplo de conteúdo:   
        {
            "email": "batatda@mail.com",
            "password": "$2a$10$5EBjCmTN3LsE5bAG/jf3PO9PsQ2EsvTLHHkVV.X.teVeBh6B8aFzS",
            "brand": "batatinha",
            "cnpj": "9837469823749",
            "adress": {
              "street": "rua potato",
              "number": "888",
              "neighborhood": "vila batata",
              "zip": "70707-707",
              "city": "casa-da-batata",
              "state": "MG"
      },
            "business": "coletor",
            "if-collector": {
              "organic": "false",
              "plastic": "true",
              "glass": "true",
              "paper": "true",
              "metal": "false",
              "battery": "false",
              "cloth": "false",
              "electronic": "false",
              "rubber": "false"
      },
            "business-size": "medio",
            "website": "batata.com",
            "image-url": "https://picsum.photos/200/300",
            "score": {
              "mensal":0,
              "anual":0
      },
            "os":[],
            "award": {},
            "complaints": [],
    }

------------------------------------------------------------------
### !! --> PERMISSÕES LOGADO <-- !!

## Exluir cadastro:
DELETE:
    https://reciclatonapi.herokuapp.com/664/users/${id}

        Para autorização:
                Authorization: 'Bearer(<-- nescessário) token_aqui', 
                Content-Type: 'application/json'

--------------------------------------------------------------------

## Alterar cadastro:
PATCH: 
    https://reciclatonapi.herokuapp.com/664/users/${id}

        Para autorização:
                Authorization: 'Bearer(<-- nescessário) token_aqui', 
                Content-Type: 'application/json'

    Exemplo de conteúdo:

        {
	        "cnpj": '22.222.222.222'
        }

----------------------------------------------------------------------

## Enviar Denuncia:

POST:
    https://reciclatonapi.herokuapp.com/664/services/

    Exemplo de conteúdo:

        {
    "contratante_id": n,
    "contratado_id": n,
    "contribuicao":n,
    "quantidade_estimada": "em-sacos-de-lixo-200L",
    "materiais":{
        "organic": "trueOrFalse",
        "plastic": "trueOrFalse",
        "glass": "trueOrFalse",
        "paper": "trueOrFalse",
        "metal": "trueOrFalse",
        " battery": "trueOrFalse",
        "cloth": "trueOrFalse",
        " electronic": "trueOrFalse",
        "rubber": "trueOrFalse"
    },
    "id": n,
    "status":"em-aberto||aceito||em-andamento||finalizado||cancelado",
    "avaliacao-contratado": n,
    "avaliacao-contratante": n,
    "endereço-de-busca":{
        "street": "Avenida Marquês de São Vicente",
        "number": 43,
        "neighborhood": "Jardim Paulista",
        "zip": "25052872",
        "city": "Santa Bárbara",
        "state": "BA"
    }
}
----------------------------------------------------------------------

## Enviar Denuncia:

POST:
    https://reciclatonapi.herokuapp.com/complaint

    Exemplo de Conteúdo:

            {
                "nome":"xxxxx",
                "email":"xxxx@xxx.xxx",
                "foto":"url_image",
                "id": 5,
                "id_denunciado": 2,
                "mensagem_denuncia":"xxxxxxxxxxxxx",
                "reviews": 2,
                "indicted":1,
                "innocent":1
        }