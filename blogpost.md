tuleap.js.io.hipster: MV* frameworks investigations
====================================================

Context
-------
Hypothesis :

- We could have good performances when handeling a lot data on the same page and while having advanced manipulations like darg'n'drop and filter. (no page refresh)
- This could be done with well structured code (We are not masters of front-end application architecture) and produce good results with only a few lines.

We decided to test some MV* framework with compatible licences and which handle two-way data binding.

Data-binding for dummies
------------------------
Frameworks which allow data-binding provide a strong connexion between the model and the view. When the model is modified, the view handles these modifications and vice versa. Such javascript frameworks allow to have both the model and the view on the front-end. We can then implement an observer which will notify the backend when the model is modified.

More details on the [angular documentation](https://docs.angularjs.org/guide/databinding).

Candidates
----------
- VanillaJS
- [Knockout](http://knockoutjs.com/) (MIT): a small data-binding framework
- [Angular](https://angularjs.org/) (MIT) : developped by Google, one of the biggest MVW framework on the market

How did we proceed
------------------
We were 4 developers and we had 2 weeks to validate the hypothesis. We choose to split into two sub-teams and learn and test one framework on each side.

After 6 days implementing prototypes, the two teams discussed and explained why their frameworks were awesome. 

Finally, one framework was choosen and we tried to validate the hypothesis.

[Browserify](http://browserify.org/) was choosen to handle libraries dependencies (jQuery...)


Knockout team
-------------

Knockout is very light, it only handles two-way data binding. If we wanted to add new features (like routing), we would have to use an external library. 
Thanks to the [great tutorial](http://learn.knockoutjs.com/#/?tutorial=intro), it was easy to master the framework and [implement new features](http://knockoutjs.com/documentation/custom-bindings.html).

Comment on a structuré le bouzin :

View <-> ViemModel <-> Model

Le ViewModel est connecté via knockout à la vue. Les elements à binder avec le model sont déclarés grâce aux bindings knockout

*Extrait de code de la vue montrant les attributs bindings*

Du côté du modèle, il s'agit de bêtes "classes" javascript, avec certains attributs liés à la view à l'aide de méthodes fournies par knockout (ko.observe pour que la view prenne la valeur du modèle, ko.value pour que le modèle prenne la valeur d'un input de la vue, etc)
 


Angular team
------------

Faut prendre un peu de temps pour comprendre avant de commencer "What da fuck is this error?"
Structurant
On a trouvé des exemples (pas tjs très clairs)


VanillaJS
---------
Problemes de performances sur les deux frameworks (Sur IE 9) (dragndrop)
On a réfléchi à la piste vanilla js :

- Tout réimplémenter à la main ?
- Utiliser des libs externes ?

Coût super élevé ? As t on les compétences pour arriver au même résultat et structurer une grosse application js


What did we choose and why
--------------------------
First, I must say that we thought that knockout.js is a great framework with great documentation, easy to learn and extend. But...

Angular has :

- features we could need in the future
- a bigger community
- more experts to hire

Whatsmore, Angular is more structured (and our javascript is somewhat less), so by applying good practices, we know we will be doing it the right way.

![knockedout](knockoutvsangular.gif)

*knocked out*


