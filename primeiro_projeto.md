## Primeiro projeto

> Lembrar de rodar tudo no virtualenv. É necessário ativar usando: 
```
source myvenv/bin/activate
```
* Rodar o comando abaixo para iniciar o projeto:
```
django-admin startproject mysite .
```
> O ponto . é crucial por que ele diz para o script instalar o Django no diretório atual (o ponto . é um atalho para referenciar este diretório). 'mysite' foi o nome escolhido para o projeto.
> django-admin é um script que criará os diretórios e arquivos.
```
projeto
├───manage.py
├───mysite
│        settings.py
│        urls.py
│        wsgi.py
│        __init__.py
└───requirements.txt
```
> manage.py é um script que ajuda com a gestão do site. Com ele, podemos iniciar um servidor de web no computador sem instalar nada, entre outras coisas.
> O arquivo settings.py contém a configuração do site.
> O arquivo urls.py contém uma lista dos padrões usados por urlresolver.

## Mudando as configurações

> Para fazer algumas alterações no mysite/settings.py. Abrir o arquivo usando o
> editor de código

* Modificar a lina TIME_ZONE para escolher o próprio fuso horário:
```
TIME_ZONE = 'America/Sao_Paulo'
```
* para alterar o idioma é preciso alterar a linha LANGUAGE_CODE:
```
LANGUAGE_CODE = 'pt-BR'
```
* Acrescentar uma nova variável no final do código para adicionar o caminho para os arquivos estáticos.
```
STATIC_ROOT = os.path.join(BASE_DIR, 'static')
```
> Quando DEBUG for True e ALLOWED_HOSTS estiver vazia, o domínio do site será validado como ['localhost:8000', '127.0.0.1', '[::1]']

* Configurar o banco de dados

> sqlite3 é o padrão do Django.

* Para criar o banco de dados é preciso executar o comando abaixo:
```
python manage.py migrate 
```
> precisamos estar no diretório que contém o arquivo manage.py

#### Iniciar o servidor web:
```
python manage.py runserver
```
> É precisa estar no diretório que contém o arquivo manage.py

Agora é só abrir o navegador e digitar o endereço localhost:8000
> Uma tela de boas vindas deve aparecer se tudo der certo!
