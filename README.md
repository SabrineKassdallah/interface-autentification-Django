1:Installation de Django
sudo pip3 install Django (pip3 car vous etes utlise python3)

trouver la version:
python -m django --version

Créer un projet :
django-admin startproject mysite:(mysite nom de
projet)

pour l’exécuter le code python manage.py runserver
ecrire dans le navigateur : http://127.0.0.1:8000/

8000:est le port par défaut
si vous volez changer le port juste taper dans le terminal
python manage.py runserver 0:8000

Création de l'application:
dans le dossier mysite taper python3 manage.py startapp polls après ce commande vous avez un nouveau répertoire nommé polls dans ce dossier on a des fichier parmis le fichier il y’a un fichier nommé views.py
from django.http import HttpResponse
def index(request):
    return HttpResponse("Hello, world. You're at the polls index.")

dans cet ligne de code on va envoyer une requete de client vers server
la repence revient de server au client  : Hello, world. You're at the polls index

dans le dossier polls on va ecrire dans le fichier urls.py  :
///////////////
from django.urls import path
from . import views
urlpatterns = [
   path('', views.index, name='index'),]

dans le dossier mysite encore un autre  dossier a5er mommé mysite on va ouvrir le fichier urls.py et ecrire 
//////
from django.contrib import admin
from django.urls import include, path
urlpatterns = [
   path('polls/', include('polls.urls')),
   path('admin/', admin.site.urls),
]
