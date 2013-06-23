#Framework css
#Bootstrap 2 - Bootstrap3 - JqueryMobile

test de packages css pour le starter-kit laravel 4


-----

##Inclus

* css-js-img
* une seule vue de test : frontend/layout
* Modeles de micro templates (non utilisés)


-----

##Exigences
- Laravel 4
- starter-kit fr

-----

##Installation 

recupérer le starter-kit fr

Ajouter le(s) framework au composer.json :
  "papajoker/bootstrap2" : "@dev",
  "papajoker/bootstrap3" : "@dev",
  "papajoker/jquerymobile" : "@dev"

en ligne de commande, faire un `(php) composer(.phar) update`

      php artisan asset:publish
	ou individuellement
      php artisan asset:publish papajoker/bootstrap2
      php artisan asset:publish papajoker/bootstrap3
      php artisan asset:publish papajoker/jquerymobile

-----

##Configuration 

Pour passer - charger le frameworkcss  :

###1) dans app/config.view.php
 remplacer `'paths' => array(__DIR__.'/../views'),`
 par `'paths' => array(public_path().'/packages/papajoker/jquerymobile/views',app_path().'/views'),`

>cette ligne est très importante :
>dans app/config.view.php nous disont a laravel ou trouver les vues,
>nous lui demandons de charger les vues "normales"(/app/views/) si non trouvées dans le frameworkcss

-----

## Passer d'un framework a un autre

dans app/config.view.php
modifier `paths`

-----

## utilisation
    Ajoutez,modifiez vos vues dans /app/views/
    pour les vues spécifiques au framework css préférez le dossier /public/packages/.../views/
    
>sous linux il est facile de faire un lien du dossier /public/packages/.../views/ dans /app/ ces 2 dossiers deviennent le même mais avec 2 entrées différentes.
> ln -s source_Packkage lien_symb_App a ce moment la + possible de passer d'un framework a un autre
> pour les dev win il y a mklink

il est possible aussi d'utiliser des namesspace avec les vues:
    View::addNamespace('frameworkcss', '/public/frameworkcss/views');
    return View::make('frameworkcss::view.name');

-----

> bootstrap3 : le layout est celui de bootstrap2, pas vraiment utilisable!
> ces frameworks n'ont qu'une seule vue particulière : /frontend/layouts/default.blade.php
