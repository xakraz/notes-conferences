1-Homebrew_differently
----------------------

<!-- MarkdownTOC -->

- [1 - We use github fork-based contribution](#1---we-use-github-fork-based-contribution)
- [2 - Ruby DSL](#2---ruby-dsl)
- [3 - Does not use ROOT user](#3---does-not-use-root-user)
- [4 - Version manager](#4---version-manager)
- [5 - Avoid patching projects](#5---avoid-patching-projects)
- [6 - Accepts niche / New projects](#6---accepts-niche--new-projects)

<!-- /MarkdownTOC -->



# 1 - We use github fork-based contribution

Pro:
++ Rely on community
++ Rely on upstream / vanilla code
++ Rely on code scm issues

Cons:
-- Lots of contributor
-- lots of PR to review



# 2 - Ruby DSL

* Still Ruby (Allow quick and easy hack)
* Still a DSL "describing"
=> Easy



# 3 - Does not use ROOT user

* Leverage /usr/local
* Focus on user in userspace



# 4 - Version manager

* Rely on Git
* Use prefix `pkg_name/version/`
  - Allow quick and easy upgrade / rollback process



# 5 - Avoid patching projects

* Most vanilla as possible
* Or use TAP mechanisme



# 6 - Accepts niche / New projects





