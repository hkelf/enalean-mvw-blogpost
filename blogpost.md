tuleap.js.io.hipster : MV* frameworks investigations
====================================================

Context
-------
Hypothesis :

- We could have good performances when handeling a lot data on the same page and while having advanced manipulations like darg'n'drop and filter. (no page refresh)
- This could be done with well structured code (We are not masters of front-end application architecture) and produce good results with only a few lines.

We decided to test some MV* framework with compatible licences and which handle two-way data binding.

Data-binding ?
--------------
Frameworks which allow data-binding provide a strong connexion between the model and the view. When the model is modified, the view handles these modifications and vice versa. Such javascript frameworks allow to have both the model and the view on the front-end. We can then implement an observer which will notify the backend when the model is modified.

More details on the [angular documentation](https://docs.angularjs.org/guide/databinding)

Candidates
----------
- [Angular](https://angularjs.org/) (MIT) : developped by Google, one of the biggest MVW framework on the market
- [Ember](http://emberjs.com/) (MIT)   : a framework with a big community
- [Knockout](http://knockoutjs.com/) (MIT): a small data-binding framework

How did we proceed
------------------
We were 4 developers and we had 2 weeks to validate the hypothesis. We choose to split into two sub-teams and learn and test one framework on each side.

After 6 days implementing prototypes, the two teams discussed and explained why their frameworks were awesome. 

Finally, one framework was choosen and we tried to validate the hypothesis.

[Browserify](http://browserify.org/) was choosen to handle libraries dependencies (jQuery...)

<del>Ember</del>Knockout team
-----------------------------
In order to install the last stable release of ember, we had to use [bower](http://bower.io/)(a front-end package manager). But to install bower, we had to install [npm](https://www.npmjs.org/)(another package manager) before.

In summary, we had to install two package managers to install emberjs (the last version of ember on npm was 1.0.0, and the stable version of ember was the 1.5.1...). There was also another issue when using browserify: it only searches dependencies in npm packages and not in bower packages (ember..).

![knockedout](byeEmber.gif)

*Bye bye ember, hello knockout !*

Instead of emberjs, the stable version of knockout can be installed only through npm. So we didn't need bower.

Knockout is very light, it only handles two-way data binding. If we wanted to add new features (like routing), we would have to use an external library. 
Thanks to the [great tutorial](http://learn.knockoutjs.com/#/?tutorial=intro), it was easy to master the framework and [implement new features](http://knockoutjs.com/documentation/custom-bindings.html).

Angular team
------------
TODO

What did we choose and why
--------------------------
First, I must say that we thought that knockout.js is a great framework with great documentation, easy to learn and extend. But...

Angular has :

- features we could need in the future
- a bigger community
- more experts to hire

Whatsmore, angular is more structured (and our js is somewhat less), so by applying good practices, we know we will be doing it the right way.

![knockedout](knockoutvsangular.gif)

*knocked out*


