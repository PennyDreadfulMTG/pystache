==================================================
 Contents of the ``.pre-commit-config.yaml`` file
==================================================

The file ``.pre-commit-config.yaml`` is used to configure the program
``pre-commit``, which controls the setup and execution of `Git hooks`_.

The ``.pre-commit-config.yaml`` file has a list of git repos, each repo may
define one or more hooks.

In this document we will review the various hooks. Some of the hooks will
modify files, some will not.

.. _pre-commit: https://pre-commit.com
.. _Git hooks: https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks


Hook Descriptions
=================

Basic warning checks include:

* ``check-added-large-files``
* ``check-case-conflict``
* ``check-executables-have-shebangs``
* ``check-shebang-scripts-are-executable``
* ``check-merge-conflict``
* ``detect-private-key``


``end-of-file-fixer``
---------------------

This will modify files by making sure that each file ends in a blank line.

If a commit fails due to this hook, just commit again.


``trailing-whitespace``
-----------------------

This will modify files by ensuring there is no trailing whitespace on any line.

If a commit fails due to this hook, just commit again.

``mixed-line-ending``
---------------------

This will modify files by ensuring there are no mixed line endings in any file.

If a commit fails due to this hook, just commit again.

``check-yaml``
--------------

This will NOT modify files. It will examine YAML files and report any
issues. The rules for its configuration are defined in
``.pre-commit-config.yaml`` in the ``exclude`` section.

If a commit fails due to this hook, all reported issues must be manually
fixed before committing again.

``ffffff``
----------

(fork of ``black`` with single-quote normalization)

This will modify Python files by re-formatting the code. The rules
for the formatting are defined in ``.pre-commit-config.yaml`` in the
``args`` section, and should match the rules in ``pyproject.toml`` (for
example the line-length must be the same).

If a commit fails due to this hook, just commit again.

``flake8``
----------

This will NOT modify files. It will examine Python files for adherence to
PEP8 and report any issues. Typically ``black`` will correct any issues that
``flake8`` may find.  The rules for this are defined in ``.flake8``, and must
be carefully selected to be compatible with ``black``.

If a commit fails due to this hook, all reported issues must be manually
fixed before committing again (if not corrected by black/ffffff).

``autoflake``
-------------

This will modify Python files by re-formatting the code. The rules
for the formatting are defined in ``.pre-commit-config.yaml`` in the
``args`` section.

``pylint``
----------

This will NOT modify files. It will examine Python files for errors and code
smells, and offer suggestions for refactoring.  The rules for the formatting
and minimum score are defined in ``.pre-commit-config.yaml`` in the ``args``
section.  If the score falls below the minimum, the commit will fail and you
must correct it manually before committing again.

``bandit``
----------

This will NOT modify files. It will examine Python files for security issues
and report any potential problems.  There is currently one allowed issue (in
the baseline.json file) in the spec testing code.  Any issues found in
non-test code must be resolved manually before committing again.

``beautysh``
------------

This will modify files. It will examine shell files and fix some
formatting issues. The rules for its configuration are defined in
``.pre-commit-config.yaml`` in the ``args`` section.

If a commit fails due to this hook, review the proposed changes in the
console, and check the files using ``git diff <file1> <file2> ...``

Doc formatting (.rst files)
---------------------------

* blacken-docs
* doc8
* pygrep

  - rst-backticks
  - rst-directive-colons
  - rst-inline-touching-normal


The blacken-docs tool will check for (and correct) any issues with python code
blocks in documentation files; the latter checks will NOT modify files. They
will examine all RST files (except ChangeLog.rst) and report any issues.

If a commit fails due to the (non)blacken-docs hooks, all reported issues must be
manually fixed before committing again.
