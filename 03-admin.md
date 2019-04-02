#### Para adicionar, editar e deletar os posts que acabei de modelar, usarei o admin do Django.
> Abrir o arquivo blog/admin.py e substituir seu conteúdo por isso:
```
from django.contrib import admin
from .modes import Post

admin.site.register(Post)
```
> Para fazer login, é preciso criar um superusuário (superuser) - uma conta de usuário que pode controlar tudo no site. Voltar à linha de comando,e  digita:
```
 python manage.py createsuperuser
```
> Depois disso éso fornecer os dados para criação do superuser e voltar ao
> navegador para fazer login

