## Realizando o primeiro deploy

> é preciso criar um repositório no github e configurar o .gitignore
```
*.pyc
*~
__pycache__
myvenv
db.sqlite3
/static
.DS_Store
```
> fazer o git push do repositorio local para o github
#### utilizando o pythonanywhere
> Utilizarei o pythonanywhere porque é gratuito para aplicações pequenas
- Criar uma conta gratuita no PythonAnywhere
- Criar um token API do PythonAnywhere, Encontrar o link no lado direito superior da página "Accounts", e então selecionar a aba "API token" e clicar no botão que diz "Create new API token".
- Navegar para a Dashboard do PythonAnywhere clicando no logo e escolher a opção de iniciar um console "Bash" -- essa é a versão do PythonAnywhere da linha de comando, igual à que existe no computador.
- Digitar no console do PythonAnywhere:
```
pip3.6 install --user pythonanywhere
```
- Agora vou executar a ferramenta para configurar a aplicação a partir do GitHub automaticamente.
```
pa_autoconfigure_django.py https://github.com/<your-github-username>/my-first-blog.git
```
-Acessar o diretório do manage.py e criar um superuser:
```
python manage.py createsuperuser
```
#### ESTÁ NO AR!

> Clicar na aba "Web" do PythonAnywhere para pegar o link do site.

