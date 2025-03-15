# Modificando o formulario de usuário do Django

## Descrição
Para fins de estudos, esse projeto é uma implementação de um sistema de autenticação e gerenciamento de usuários utilizando Djago, porém com um modelo de usuário personalizado. Extendendo o modelo `AbstractUser` sobrescrevendo o campo de email e tornando-o campo de login, e alterando os campos 'first_name', 'last_name' para 'name', e por fim criando um novo campo que chama 'bio'.

## Estrtura dos diretórios
```
├── .gitignore
├── .python-version
├── README.md
├── pyproject.toml
├── src
    ├── base
    │   ├── __init__.py
    │   ├── admin.py
    │   ├── apps.py
    │   ├── migrations/   # pasta com as migrações do db
    │   │   └── ...
    │   ├── models.py
    │   ├── tests.py
    │   └── views.py
    ├── custom_user
    │   ├── __init__.py
    │   ├── asgi.py
    │   ├── settings.py
    │   ├── urls.py
    │   └── wsgi.py
    ├── db.sqlite3
    └── manage.py
└── uv.lock
```

## Componentes do projeto
`base/`
- contem o código relacionado a personalização do modelo de usuário e administração
    - `models.py`: Contém o modelo 'User', que estende 'AbstractUser' do Django, e faz as alterações descritas.
    - `admin.py`: Registra o modelo User no painel de administração.

`custom_user/`
- contém o código de configuração do projeto e os arquvios de inicialização
    - `settings.py`: Arquivo de configurações do Django. Define configurações como `INSTALLED_APPS`, etc...

## Como executar
1. Clone o repositório
```
git clone https://github.com/esteveseverson/django-custom-user
cd django-custom-user
```
2. Esse projeto utiliza [uv](https://docs.astral.sh/uv/) como gerenciador de pacotes
```
uv install
uv run manage.py migrate
```
3. Crie um superuser para acessar o admin
```
uv run manage.py createsuperuser
```
4. Inicie o servidor
```
uv run manage.py runserver
```
5. Acesse a interface administrativa em `https://127.0.0.1:8000/admin` com o superusuário criado
---