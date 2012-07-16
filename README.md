Django-Ubigeo-Peru
====================

django-ubigeo-peru, es una app que te permitira implementar facilmente 
los ubigeos de Perú, en tus django app.


Dependencias
------------

1. Python 

  * south

2. Javascript

  * jquery


Instalar
--------

En tu settings.py

>    
>    INSTALLED_APPS = ( 
>
>        ......    
>        'ubigeo',
>    
>    )
>    


En tu urls.py

>    
>    urlpatterns = patterns('',
>    
>        .....
>        (r'^ubigeo/', include('ubigeo.urls')),
>        
>    )
>    


Usar
-----

En tu models.py:

>    
>    from ubigeo.models import Ubigeo
>    
>    class MyModel(models.Model):
>        name = models.CharField(max_length=120)
>        ubigeo = models.ForeignKey(Ubigeo)
>    

en tu forms.py:

>    
>    from ubigeo.models import Ubigeo
>    from ubigeo.fields import UbigeoFormField
>    fron ubigeo import constant
>
>    class MyModelForm(form.ModelForm):
>        ubigeo = UbigeoFormFiel(ubigeo=constant.ALL)
>    
>        class Meta:
>            model = Ubigeo
>    

ahora tienes opciones:
  ONLY_PERU
  ONLY_INTERNATIONAL
  ALL
