# Designing CLI tool that people lovs

<!-- MarkdownTOC -->

- [Links](#links)
- [Principales](#principales)
- [Tooling](#tooling)
- [Tips](#tips)

<!-- /MarkdownTOC -->


##Links

Slides:
- https://carolynvanslyck.com/talk/go/cli/#/

Repos:
- https://github.com/carolynvs?tab=repositories
- https://porter.sh



## Principales

>
> Cli tools are not thinked ahead or designed ...
> Features come haphazardly
>


"As a team, agree on a grammar"

You can disagree but you should not make the life of others harder



## Tooling

* `spf13/cobra` - Commands and Flags
* `spf13/viper` - Configuration Management
* `spf13/afero` - File System Abstraction



## Tips

* Make *functions* that are 1:1 the *commands* in your CLI
* Create happy little packages for everything -> Hide your *band-aides* and API wrappers in here


