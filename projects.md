---
title: /projects
layout: projects
permalink: /projects/
---

# AbMSA

Code goes here.

<br /><br />python:
{% highlight python %}
def func():
     # function body
     print("hello world!")

     def setup(app):
         # enable Pygments json lexer
         try:
             import pygments
             if pygments.__version__ >= '1.5':
                 # use JSON lexer included in recent versions of Pygments
                 from pygments.lexers import JsonLexer
             else:
                 # use JSON lexer from pygments-json if installed
                 from pygson.json_lexer import JSONLexer as JsonLexer
         except ImportError:
             pass  # not fatal if we have old (or no) Pygments and no pygments-json
         else:
             app.add_lexer('json', JsonLexer())

         return {"parallel_read_safe": True}

words = ['cat', 'window', 'defenestrate']
for w in words:
   print w, len(w)
{% endhighlight %}

## HTML/CSS/JavaScript

Code goes here
<br /><br />python:
{% highlight python %}
def func():
     # function body
     print("hello world!")

     def setup(app):
         # enable Pygments json lexer
         try:
             import pygments
             if pygments.__version__ >= '1.5':
                 # use JSON lexer included in recent versions of Pygments
                 from pygments.lexers import JsonLexer
             else:
                 # use JSON lexer from pygments-json if installed
                 from pygson.json_lexer import JSONLexer as JsonLexer
         except ImportError:
             pass  # not fatal if we have old (or no) Pygments and no pygments-json
         else:
             app.add_lexer('json', JsonLexer())

         return {"parallel_read_safe": True}

words = ['cat', 'window', 'defenestrate']
for w in words:
   print w, len(w)
{% endhighlight %}

