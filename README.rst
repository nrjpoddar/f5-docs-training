Welcome to F5's Open Source Documentation Training!
===================================================

This training demo is intended to teach F5 Networks' software engineers to create documentation for open source projects. For these projects, documentation is created as part of the agile development process. All software engineers are expected to create documentation for the tools/features they are developing.

All docs content is curated by an editor, who ensures compliance with established style guidelines; formats content for reuse; and prepares content for publication in conjunction with product releases.

.. note::

    This training exercise supplements the F5 Open Source Documentation Training presentation. Explanations of the concepts and tools are provided in `f5-opensource-docs-training <https://f5-my.sharepoint.com/personal/j_putrino_f5_com/_layouts/15/guestaccess.aspx?guestaccesstoken=Xe1%2f7HpYVLat%2fsEsOtHNnLvL%2bN5P4yWMrl22i5FhTqs%3d&docid=2_18c88415fb4cd452ea59275e63f7c3580&rev=1>`_ (PPT).

Project Setup
-------------

Take the steps below to clone the training repo from GitHub and install the project requirements.

.. tip:: You may wish to do this in a virtual environment to avoid conflicts with existing versions of the project requirements or their dependencies.

.. code-block:: bash

    git clone https://github.com/jputrino/f5-docs-training.git
    cd f5-docs-training
    pip install –r requirements.docs.txt

Check out a new branch to which you will commit your work.

.. code-block:: bash

    git checkout -b feature.<yourname>


Create New Content
------------------

#. Make a new file that follows the file-naming conventions shown below. **Be sure to put it in the** ``docs/includes`` **directory**.

    * topic: topic_name-of-feature.rst
    * concept: concept_descriptive-file-name.rst
    * reference: ref_descriptive-file-name.rst

#. Use the feature template to create a new topic.

    .. tip::

        * Can be about any subject you like; keep it clean and professional.
        * See the :ref:`examples` for ideas.

#. **Optional**: Create additional feature topics to be :ref:`combined into a map <Create a Document Map>`.

#. Save and commit your work.

    The commands below will add your work to version control and commit it.

    .. code:: bash

        git add --all
        git commit -m "my first feature topic"


#. Push your work to GitHub.


.. important::

    In a development environment, it's more likely that you'd push your work to your fork of a project, then open a pull request into the parent, or 'upstream', repo when it's ready for review.

    Your documentation efforts should fit smoothly into your existing development workflow. Include your code **and** your documents in the same pull request and tag/assign your editor **in addition to** your code reviewers.


Create a Document Map
---------------------

Feature topics are combined into documents (i.e., guides) via maps. In `sphinx <http://www
.sphinx-doc.org/en/stable/>`_, the ``.. include::`` directive provides the
means for importing content from one file into another. In general, maps
should live in a directory higher than the content they will be reusing. So,
 if feature topics live in ``docs/includes``, maps should just live in
 ``docs/``.

1. Make a new file that follows the file-naming convention and architecture described in the `training slides <https://f5-my.sharepoint.com/personal/j_putrino_f5_com/_layouts/15/guestaccess.aspx?guestaccesstoken=7ZEBHlnODDNSA6mJLYoN3Uqxjshez3gP96vlO%2bchxmU%3d&docid=08c88415fb4cd452ea59275e63f7c3580&rev=1>`_.

.. topic:: Filename Example

    "map_feature-documentation-training.rst"

2. Use the ``.. include::`` directive to pull your content into the map.

.. topic:: Map Example

    .. code-block:: text

        Salsa
        =====

        .. include:: includes/concept_overview.rst

        .. include:: includes/topic_feature1.rst

        .. include:: includes/topic_feature2.rst


3. Commit your work and push it to GitHub.


View Your Documentation
-----------------------

.. topic:: Option 1: Build locally

    When creating documentation, it's a great idea to build the docs locally and review them periodically.

    1. Run the command ``make html`` to build the documentation.

    2. View the files in the ``docs/_build/html directory`` in your browser.


.. topic:: Option 2: View online

    The training project repo is set up to build automatically on Read the Docs whenever content is pushed to any branch.

    Go to ``http://f5-docs-training.readthedocs.io/en/<your-feature-branch>`` to view your documentation!


.. toctree::
    :hidden:

    self
    docs/sphinx_rst_cheat-sheet
    Example Map 1 <docs/map_example1>
    Example Map 2 <docs/map_example2>
    Example Content <docs/includes/README>

Next Steps
----------

* Read the `F5 Open Source Documentation Style Guide <http://f5-openstack-docs.readthedocs.io/en/latest/style_guide.html>`_.
* Check out the `feature documentation cheat sheet <http://f5-openstack-docs.readthedocs.io/en/latest/quick-ref-how-to-document-feature.html>`_.
* Check out the `API documentation cheat sheet <http://f5-openstack-docs.readthedocs.io/en/latest/quick-ref-how-to-document-api.html>`_.

