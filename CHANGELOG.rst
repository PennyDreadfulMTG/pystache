v0.6.5 (2023-08-19)
-------------------

Other
~~~~~

- Keep changelog up to date manually as I don't know how to autogenerate. [Thomas David Baker]
- Remove versioningit because it makes packaging hard for Linux distrubutions. [Thomas David Baker]

v0.6.4 (2023-08-13)
-------------------

Other
~~~~~

- Merge pull request #23 from PennyDreadfulMTG/more-fixes. [Thomas David Baker]
- Use the content-type for RST that pypi now wants
- Use the content-type for RST that pypi now wants. [Thomas David Baker]

v0.6.3 (2023-08-13)
-------------------

New
~~~

- Add full sphinx apidoc build, include readme/extras. [Stephen L Arnold]
    * add new tox commands for 'docs' and 'docs-lint'
    * cleanup link errors found by docs-lint
    * add sphinx doc build workflow, update ci workflow
    * remove new version var from init.py globals

- Display repo state in docs build, include CHANGELOG. [Stephen L Arnold]
    * add sphinx_git extension to docs conf and setup deps
    * display branch/commit/state docs were built from
    * include CHANGELOG (but not HISTORY) in docs build/toc
    * Convert readme.md to readme.rst, move extra docs. [Stephen L Arnold]

Fixes
~~~~~

- Fix included filename and link cleanup. [Stephen L Arnold]
- Remove more py2 cruft from doctesting (py3.10 warnings) [Stephen L Arnold]
- Update maintainer info and spec test cmd. [Stephen L Arnold]
    * update coverage value for delta/base, allow digits only
- Use updated bandit action and workflow excludes (exclude test) [Stephen L Arnold]
    * also fix missing PR event check in coverage workflow
- Use current org-level coverage workflow. [Stephen L Arnold]
    * increase fetch depth and update regex
    * updated action deps, relaxed run criteria
    * go back to "normal" tokens, remove permission hacks
    * still needs more job isolation => refactor for another day

Other
~~~~~

- Merge pull request #21 from PennyDreadfulMTG/update-pypi. [Thomas David Baker]
- Update a few small things before making a release for pypi
- Update location of flake8 for pre-commit, official location has moved. [Thomas David Baker]
- Correct small issue in README. [Thomas David Baker]
- Specify passenv in a way that tox is happy with. [Thomas David Baker]
- Ignore PyCharm dir. [Thomas David Baker]
- Update TODO to remove some things that have been TODOne. [Thomas David Baker]
- Merge pull request #20 from VCTLabs/new-docs-cleanup. [Katelyn Gigante]
- New docs cleanup
- Merge pull request #19 from VCTLabs/auto-docs. [Thomas David Baker]
- New docs and automation, more modernization
- Do pre-release (manual) updates for changes and conda recipe. [Stephen L Arnold]
    * create changes file: gitchangelog v0.6.0.. > CHANGELOG.rst
    * edit top line in CHANGELOG.rst using current date/new tag
    * edit conda/meta.yaml using new tag, then tag this commit
- Merge pull request #18 from VCTLabs/mst-upstream. [Thomas David Baker]
- Workflow and test driver fixes
- Use buildbot account. [Katelyn Gigante]
- Merge pull request #16 from PennyDreadfulMTG/fix-coverage. [Katelyn Gigante]
- Use ACCESS_TOKEN secret rather than provided GITHUB_TOKEN
- Use ACCESS_TOKEN secret rather than provided GITHUB_TOKEN. [Katelyn Gigante]
- Should fix the coverage badge

v0.6.2  (2022-09-14)
--------------------

New
~~~
- Add full sphinx apidoc build, include readme/extras. [Stephen L
  Arnold]

  * add new tox commands for 'docs' and 'docs-lint'
  * cleanup link errors found by docs-lint
  * add sphinx doc build workflow, update ci workflow
  * remove new version var from __init__.py globals

Changes
~~~~~~~
- Convert readme.md to readme.rst, move extra docs. [Stephen L Arnold]

Fixes
~~~~~
- Fix included filename and link cleanup. [Stephen L Arnold]
- Remove more py2 cruft from doctesting (py3.10 warnings) [Stephen L Arnold]
- Update maintainer info and spec test cmd. [Stephen L Arnold]

  * update coverage value for delta/base, allow digits only
- Use updated bandit action and workflow excludes (exclude test)
  [Stephen L Arnold]

  * also fix missing PR event check in coverage workflow
- Use current org-level coverage workflow. [Stephen L Arnold]

  * increase fetch depth and update regex
  * updated action deps, relaxed run criteria
  * go back to "normal" tokens, remove permission hacks
  * still needs more job isolation => refactor for another day

Other
~~~~~
- Use buildbot account. [Katelyn Gigante]
- Use ACCESS_TOKEN secret rather than provided GITHUB_TOKEN. [Katelyn
  Gigante]

  Should fix the coverage badge


v0.6.1 (2021-11-24)
-------------------

Changes
~~~~~~~
- Add shallow checkout for testing. [Stephen L Arnold]
- Bump comment action to latest release, verify checkout depth. [Stephen
  L Arnold]

  * see: https://github.com/marocchino/sticky-pull-request-comment/issues/298
    in upstream action repo

Fixes
~~~~~
- Use workflow PR target and checkout params. [Stephen L Arnold]
- Split coverage (checkout) job from PR comment job. [Stephen L Arnold]
- Use correct tox env cmd for single platform/version. [Stephen L
  Arnold]
