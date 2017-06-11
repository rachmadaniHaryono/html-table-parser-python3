html-table-parser-python3
=========================

This module consists of just one small class.
Its purpose is to parse HTML tables without help of external modules.
Everything I use is part of python 3.
You can install this module, or just copy the class located in *parse.py* into your own code.

Getting Started
---------------

Installing
~~~~~~~~~~

Run pip install to this repo

.. code:: bash

 pip install git+git://github.com/schmijos/html-table-parser-python3.git

Usage
~~~~~

.. code:: python

 import urllib.request
 from pprint import pprint
 from html_table_parser import HTMLTableParser
 
 target = 'http://www.twitter.com'

 # get website content
 req = urllib.request.Request(url=target)
 f = urllib.request.urlopen(req)
 xhtml = f.read().decode('utf-8')

 # instantiate the parser and feed it
 p = HTMLTableParser()
 p.feed(xhtml)
 pprint(p.tables)


*p.tables* returns nested lists of tables containing rows containig cells as string.
Tags in cells are stripped and the tags text content is joined.
The console output for parsing all tables on the twitter home page looks like this:

.. code:: python

 >>>
  [[['', 'Anmelden']],
  [['Land', 'Code', 'Für Kunden von'],
   ['Vereinigte Staaten', '40404', '(beliebig)'],
   ['Kanada', '21212', '(beliebig)'],
   ...
   ['3424486444', 'Vodafone'],
   ['Zeige SMS-Kurzwahlen für andere Länder']]]

see also example_of_usage.py

Running the tests
~~~~~~~~~~~~~~~~~

tba

Versioning
~~~~~~~~~~

We use SemVer for versioning. For the versions available, see the tags on this repository.

Authors
~~~~~~~

- schmijos - Initial work

See also the list of contributors who participated in this project.

License
~~~~~~~

This project is licensed under the AGPLv3- see the *LICENSE* file for details

Acknowledgments
~~~~~~~~~~~~~~~

- Hat tip to anyone who's code was used
