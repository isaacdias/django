## Criando uma aplicação
#### Modelos

> um modelo de Django é um tipo especial de objeto que é salvo em um banco de
> dados.

#### Criando uma aplicação
> Para manter tudo organizado, vou criar uma aplicação separada dentro do
> projeto.
> o comando deve ser executado dentro do diretório onde está o manage.py
```
python manage.py startapp blog
```
> um novo diretório será criado:
```
projeto
├── blog
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── migrations
│   │   └── __init__.py
│   ├── models.py
│   ├── tests.py
│   └── views.py
├── db.sqlite3
├── manage.py
└── mysite
    ├── __init__.py
    ├── settings.py
    ├── urls.py
    └── wsgi.py

Após criar a aplicação, é preciso informar ao Django que ele deve usá-la. Posso
fazer isso adcionando o nome da aplicação dentro do campo INSTALLED_APPS que
fica no mysite/settings.py

INSTALLED_APPS
'blog'
```
#### Criando um modelo de postagem para o blog
> No arquivo blog/models.py posso definir os objetos chamados modelos
```
from django.db import models
from django.utils import timezone


class Post(models.Model):
    author = models.ForeignKey('auth.User', on_delete=models.CASCADE)
    title = models.CharField(max_length=200)
    text = models.TextField()
    created_date = models.DateTimeField(
            default=timezone.now)
    published_date = models.DateTimeField(
            blank=True, null=True)

    def publish(self):
        self.published_date = timezone.now()
        self.save()

    def __str__(self):
        return self.title
```
> models.Model significa que o Post é um modelo de Django, então o Django sabe ele que deve ser salvo no banco de dados.
#### Criando tabelas para nossos modelos no banco de dados
> O último passo é adicionar nosso novo modelo ao banco de dados. Primeiramente, preciso fazer com que o Django entenda que fiz algumas alterações nos modelos. (acabei de criar um modelo de Post!) Poso digitar no terminal:
```
python manage.py makemigrations blog
```
> depois de preparado o arquivo, já posso migrar o arquivo para o banco de
> dados:
```
python manage.py migrate blog
```
 
