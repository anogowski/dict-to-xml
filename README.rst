==================
dict-to-xml
==================

.. image:: https://img.shields.io/pypi/v/dict-to-xml.svg
    :target: https://pypi.org/project/dict-to-xml
    :alt: PyPI version

.. image:: https://img.shields.io/pypi/pyversions/dict-to-xml.svg
    :target: https://pypi.org/project/dict-to-xml
    :alt: Python versions

.. image:: https://github.com/anogowski/dict-to-xml/actions/workflows/publish-to-test-pypi.yml/badge.svg
    :target: https://github.com/anogowski/dict-to-xml/actions/workflows/publish-to-test-pypi.yml
    :alt: See Build Status on GitHub Actions

A simple dict to xml converter

----

This project was generated with `Cookiecutter`_ along with `@hackebrot`_'s `cookiecutter-plugin`_ template.


Features
--------

* Convert dict to xml


Requirements
------------

* Python 3.11


Installation
------------

You can install "dict-to-xml" via `pip`_ from `PyPI`_::

    $ pip install dict-to-xml


Usage
-----

.. example-code::

	.. code-block:: JSON
	my_dict = {
			'name': 'The Andersson\'s',
			'size': 4,
			'members': {
				'total-age': 62,
				'child': [
					{
						'@name': 'Tom',
						'@sex': 'male',
					},
					{
						'@name': 'Betty',
						'@sex': 'female',
						'grandchild': [
							{
								'@name': 'herbert',
								'@sex': 'male',
							},
							{
								'@name': 'lisa',
								'@sex': 'female',
							},
						]
					},
				]
			},
		}

	.. code-block:: python
	xml_converter: XMLConverter = XMLConverter(my_dict, "family")
	print(xml_converter.formatted_xml)

.. example-output::

	.. code-block:: xml

	<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
	<family>
		<name>The Andersson's</name>
		<size>4</size>
		<members>
			<total-age>62</total-age>
			<child name="Tom" sex="male" />
			<child name="Betty" sex="female">
				<grandchild name="herbert" sex="male" />
				<grandchild name="lisa" sex="female" />
			</child>
		</members>
	</family>

Contributing
------------
Contributions are very welcome. Tests can be run with `tox`_, please ensure
the coverage at least stays the same before you submit a pull request.

License
-------
Dual License:

Distributed under the terms of both the `BSD-3`_ AND `Mozilla Public License 2.0`_ licenses.

"dict-to-xml" is free and open source software


Issues
------

If you encounter any problems, please `file an issue`_ along with a detailed description.

.. _`Cookiecutter`: https://github.com/audreyr/cookiecutter
.. _`@hackebrot`: https://github.com/hackebrot
.. _`MIT`: https://opensource.org/licenses/MIT
.. _`BSD-3`: https://opensource.org/licenses/BSD-3-Clause
.. _`Mozilla Public License 2.0`: https://opensource.org/license/mpl-2-0
.. _`GNU GPL v3.0`: https://www.gnu.org/licenses/gpl-3.0.txt
.. _`Apache Software License 2.0`: https://www.apache.org/licenses/LICENSE-2.0
.. _`cookiecutter-plugin`: https://github.com/dev/cookiecutter-plugin
.. _`file an issue`: https://github.com/anogowski/dict-to-xml/issues
.. _`tox`: https://tox.readthedocs.io/en/latest/
.. _`pip`: https://pypi.org/project/pip/
.. _`PyPI`: https://pypi.org/project
