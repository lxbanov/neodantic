======================
Neomodantic
======================

An extension of the `neomodel <https://github.com/neo4j-contrib/neomodel>`_ library that adds support for `pydantic <https://github.com/pydantic/pydantic>`_ models.

The library is fork of `neomodel <https://github.com/neo4j-contrib/neomodel>`_. For the documentation of the original library, see the `neomodel documentation <https://neomodel.readthedocs.io/en/latest/>`_.

Installation
------------

Install the library from pypi:

.. code-block:: bash

    pip install neomodantic

Usage
-----

The usage is no different from the original neomodel except now `StructuredNode` and `StructuredRel` are now can be used as pydantic models.

.. code-block:: python

    from neomodantic import StructuredNode, StringProperty

    class Person(StructuredNode):
        name = StringProperty(unique_index=True)

    person = Person.get_or_create(name="John Doe")
    print(person.name)
    print(person.id)
    print(person.model_dump_json())