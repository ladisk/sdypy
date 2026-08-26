Nomenclature
============

SDyPy fixes one name per quantity across all first-level packages, so that
``sdypy.EMA``, ``sdypy.model`` and the rest do not each invent their own
spelling for a damping ratio or a stiffness matrix. The canonical names are
decided by `SEP 2`_ and reproduced below.

How to use the table
--------------------

* Writing a new public function or class? Look the quantity up in the
  **Symbol** column and use that name for the parameter or attribute.
* Renaming an existing one? Find your current spelling in the **Instead of**
  column; the row tells you what to move to. Keep the old name working as a
  deprecated alias — SEP 2's deprecation policy holds it through all of v1.x.
* Quantity not in the table? The word-order guideline in SEP 2 applies, and it
  yields to an established term of art. Once settled, the name is added here so
  the decision is recorded rather than re-argued.

The table binds the **public surface** only: parameters, attributes and return
names that a caller can see. Local variables inside a numerical routine are
free to use whatever short symbols read best.

Two affix conventions ride alongside it: a count is ``n_<plural>``
(``n_modes``, ``n_nodes``), never a bare ``n``; an index is ``<name>_idx``
(``node_idx``), never ``_ind``.

Conformance is checked mechanically by ``tools/check_nomenclature.py``, which
audits a sibling clone without importing it::

    python tools/check_nomenclature.py --path ../sdypy-EMA

The canonical table
-------------------

The table below is included from its single definition in `SEP 2`_. If you are
reading this file as source on GitHub rather than on the documentation site,
the table will not appear here — GitHub does not process file includes. Read it
in `SEP 2`_ instead, where it lives.

.. include:: ../seps/sep-0002.rst
   :start-after: .. canonical-table-start
   :end-before: .. canonical-table-end

Where this comes from
---------------------

The table above is not a copy. It is transcluded from
`SEP 2`_, which is its single definition and the source of truth for both the
canonical names and the divergent spellings they replace.
Editing the SEP updates this page.

See SEP 2 itself for the governance context: the deprecation policy, the rules
for naming modules, classes and constants, the public-API surface requirements,
and the SEP's current status.


.. _SEP 2: https://sdypy.readthedocs.io/en/latest/seps/sep-0002.html
