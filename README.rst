mako-pipeline
=============

A sort of django-pipeline, but for mako.

Install
-------

mako-pipeline is avaiable on pypi::

  $ pip install mako-pipeline


Usage
-----

On your python script, call `mako_pipeline.configure` to setup file mapping::

  from mako_pipeline import configure

  configure({
      'debug': True,
      'javascript': {
          'final-js': ['file1', 'file2']
      }
  })

On templates, import the module using `namespace` tag and use like following::

  <%namespace name="assets" module="mako_pipeline.assets" />

  <%assets:tag name="final-js" args="ASSETS_URL" %>
    <script src="${ASSETS_URL}"></script>
  <%/assets:tag%>

License
-------

This project is licensed under MIT license (please see LICENSE file).