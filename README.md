# venue-connect-sound-srv

Este projeto, criado por Alexandre Magno Strukoski (nuno.perry.strukoski@gmail.com), é uma plataforma web que conecta estabelecimentos locais com bandas e músicos para facilitar o agendamento de shows. A plataforma utiliza uma API Flask RESTful para gerenciar dados de estabelecimentos, bandas e shows. Além disso, a plataforma também suporta pagamentos internos.

O código-fonte do projeto pode ser encontrado no seguinte repositório do GitHub: [https://github.com/Alex-Strukoski/venue-connect-sound-srv.git](https://github.com/Alex-Strukoski/venue-connect-sound-srv.git)

As principais bibliotecas utilizadas são:

1. Flask-Migrate - para lidar com todas as migrações de banco de dados.
2. Flask-RESTful - biblioteca de API RESTful.
3. Flask-Script - fornece suporte para escrever scripts externos.
4. Flask-SQLAlchemy - adiciona suporte para o ORM SQLAlchemy.

## Estrutura do Projeto

```
.
├── README.md
├── app.py
├── endpoints
│   ├── __init__.py
│   ├── bands
│   │   ├── __init__.py
│   │   ├── model.py
│   │   └── resource.py
│   ├── venues
│   │   ├── __init__.py
│   │   ├── model.py
│   │   └── resource.py
│   └── shows
│       ├── __init__.py
│       ├── model.py
│       └── resource.py
├── manage.py
├── requirements.txt
└── settings.py
```

## Executando

1. Clone o repositório.
2. Instale as dependências com `pip install -r requirements.txt`.
3. Execute os seguintes comandos:
   1. `python manage.py db init`
   2. `python manage.py db migrate`
   3. `python manage.py db upgrade`
4. Inicie o servidor executando `python manage.py runserver` ou utilizando os scripts [`run.bat`](command:_github.copilot.openRelativePath?%5B%22run.bat%22%5D "run.bat") ou [`run.sh`](command:_github.copilot.openRelativePath?%5B%22run.sh%22%5D "run.sh").

## Uso

### Endpoint de Bandas

POST http://127.0.0.1:5000/api/bands

REQUEST

```json
{
	"name": "Nome da Banda"
}
```

RESPONSE

```json
{
    "id": 1,
    "name": "Nome da Banda",
    "shows": []
}
```

PUT http://127.0.0.1:5000/api/bands/1

### Endpoint de Estabelecimentos

POST http://127.0.0.1:5000/api/venues

REQUEST

```json
{
	"name": "Nome do Estabelecimento"
}
```

RESPONSE

```json
{
    "id": 1,
    "name": "Nome do Estabelecimento",
    "shows": []
}
```

DELETE http://127.0.0.1:5000/api/users/1

RESPONSE

```json
{
    "id": 3,
    "name": "Tom Tom",
    "todos": []
}
```

GET http://127.0.0.1:5000/api/users

RESPONSE

```json
{
    "count": 2,
    "users": [
        {
            "id": 1,
            "name": "John John",
            "todos": [
                {
                    "id": 1,
                    "name": "First task",
                    "description": "First task description"
                },
                {
                    "id": 2,
                    "name": "Second task",
                    "description": "Second task description"
                }
            ]
        },
        {
            "id": 2,
            "name": "Smith Smith",
            "todos": []
        }
    ]
}
```

GET http://127.0.0.1:5000/api/users/2

```json
{
    "id": 2,
    "name": "Smith Smith",
    "todos": []
}
```

GET http://127.0.0.1:5000/api/users?name=John John

```json
{
    "count": 1,
    "users": [
        {
            "id": 1,
            "name": "John John",
            "todos": [
                {
                    "id": 1,
                    "name": "First task",
                    "description": "First task description"
                },
                {
                    "id": 2,
                    "name": "Second task",
                    "description": "Second task description"
                }
            ]
        }
    ]
}
```

GET http://127.0.0.1:5000/api/users?limit=1&offset=1

```json
{
    "count": 1,
    "users": [
        {
            "id": 2,
            "name": "Smith Smith",
            "todos": []
        }
    ]
}
```

Todo endpoint is similar to Users endpoint.

## Criador

Este projeto foi criado por Alexandre Magno Strukoski. Você pode entrar em contato com ele através do email [nuno.perry.strukoski@gmail.com](vscode-file://vscode-app/c:/Users/joaod/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html "mailto:&amp;#x6e;&amp;#117;&amp;#110;&amp;#111;&amp;#x2e;&amp;#112;&amp;#x65;&amp;#x72;&amp;#x72;&amp;#121;&amp;#46;&amp;#115;&amp;#x74;&amp;#114;&amp;#117;&amp;#107;&amp;#x6f;&amp;#115;&amp;#107;&amp;#x69;&amp;#64;&amp;#x67;&amp;#109;&amp;#x61;&amp;#105;&amp;#108;&amp;#46;&amp;#99;&amp;#x6f;&amp;#109;").
