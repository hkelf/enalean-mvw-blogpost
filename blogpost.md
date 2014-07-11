Tuleap.js.io.hipster: MV* frameworks investigations
====================================================


Context
-------
Some users have experienced performances issues when using the Tuleap AgileDashboard with a huge set of data. We have decided to investigate how a MV* framework could answer to these hypothesis:
    
* We could have good performances when handeling advanced manipulations (drag 'n' drop, filter...) on a lot of data, all in the same page.
* This could be done with well structured code and produce good results with only a few lines.


Candidates
----------
- [Knockout](http://Knockoutjs.com/) [MIT]: a small data-binding framework
- [AngularJS](https://angularjs.org/) [MIT]: one of the biggest MVW framework on the market
- [VanillaJS](http://vanilla-js.com/): the good ol' way to write JavaScript


Data-binding for dummies
------------------------
Frameworks which allow data-binding provide a strong connexion between the model and the view. When the model is modified, the view handles these modifications and vice versa. Such JavaScript frameworks allow to have both the model and the view on the front-end side. We can then implement an observer which will notify the backend when the model is modified.
    
More details: [AngularJS documentation](https://docs.angularjs.org/guide/databinding).


Knockout
--------
Knockout is a very light JavaScript framework, it only handles two-way data binding. If we wanted to add new features, we would have to use an external library. For exampke, we had to use jQuery to handle REST calls. We also had to implement a little algorithm to manage list filtering.

Thanks to this [great tutorial](http://learn.Knockoutjs.com/#/?tutorial=intro), it was easy to master the framework and [implement new features](http://Knockoutjs.com/documentation/custom-bindings.html).
    
**The good:**
   
* Well documented, haven't encountered difficulties to bring features which may seems complex at the first sight
* Few constraints when structuring the app
   
**The meh:**
  
* We had to pull dependencies to bring some basic features (rest), or implement them (filtering)
* Low community


AngularJS
---------
AngularJS is a complete JavaScript framework. The main idea is also, like Knockout, the data-binding, but it handles also routing, components, filtering, testing... It takes a little time to understand all the mechanic but it's very powerful.

![red-green-refacto](red-green-refacto.png)

As a **framework**, AngularJS brings us the needed structure and workflow to get things done. And as red-green-refactor aficionados, we do like the dependency injection that has been put everywhere in the stack.

**The good:**

* We found many resources on the Internet like the good AngularJS documentation which helped us to develop our spike application.
* Everything is handled by Angular, not only the data-binding
* Testing framework included


**The meh:**

* It takes a little time to master all the basics


VanillaJS
---------
Coding without knowing the best practices, we faced to performances issues (drag'n'drop, scrolling...). We knew we could fix them using our frameworks, but it forced us to ask this question: **why not coding all this new application by ourselves?** We would have needed to rewrite all the data-binding architecture, to use external libraries etc.

We didn't go further because we knew that the cost will be to expensive and we don't like to reinvent the wheel.


What did we choose and why
--------------------------
First of all, we need to compare apples with apples, and pears with pears: AngularJS have to be compared with Knockout + jQuery + a routing lib + a REST lib...

<script type="text/javascript" src="//www.google.com/trends/embed.js?hl=fr&q=angularjs+%2B+angular.js,+knockoutjs+%2B+knockout.js&cmpt=q&content=1&cid=TIMESERIES_GRAPH_0&export=5&w=600&h=330"></script>
[Complete Google trends](http://www.google.com/trends/explore#q=angularjs%20%2B%20angular.js%2C%20knockoutjs%20%2B%20knockout.js&cmpt=q)


First, I must say that we thought that Knockout.js is a great framework with great documentation, easy to learn and extend. But...
    
    AngularJS has :
    
    - features we could need in the future
    - a bigger community
    - more experts to hire
    
    Whatsmore, AngularJS is more structured (and our JavaScript is somewhat less), so by applying good practices, we know we will be doing it the right way.
    
    ![knockedout](knockoutvsangular.gif)
    
    *knocked out*


