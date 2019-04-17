## urls

#### Como funcionam as URLs em Django?
> Abra o arquivo mysite/urls.py no seu editor de código preferido e veja o que aparece:
```
"""mysite URL Configuration

[...]
"""
from django.urls import path, include
from django.contrib import admin

urlpatterns = [
    path('admin/', admin.site.urls),
]
```
## primeira URL no Django!
> É hora de criar nossa primeira URL! Queremos que http://127.0.0.1:8000 / seja a página inicial do nosso blog e exiba uma lista de posts.

Também queremos manter o arquivo de mysite/urls.py limpo, e portanto importaremos as URLS da nossa aplicação blog no arquivo principal mysite/urls.py.

Adicione uma linha para importar blog.urls. Note que estamos usando a função include, então você também precisará importar esta função.

O seu arquivo mysite/urls.py deve agora se parecer com isto:
```
mysite/urls.py

from django.urls import path, include
from django.contrib import admin

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('blog.urls')),
]
```
## blog.urls
> Crie um novo arquivo vazio chamado urls.py no diretório blog. É fácil! Basta adicionar essas duas linhas:
```
blog/urls.py

from django.urls import path
from . import views
```
> Aqui, estamos importando do Django a função url e todas as nossas views do aplicativo blog. (Não temos nenhuma ainda, mas chegaremos a isso em um minuto!)

Depois disso podemos adicionar nosso primeiro padrão de URLs:
```
blog/urls.py

urlpatterns = [
    path('', views.post_list, name='post_list'),
]
```

