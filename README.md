<h1 align="center">
<img src="https://raw.githubusercontent.com/songtianlun/frytea-docs/master/docs_sample/images/Frytea-logo-green-3x.png" alt="Frytea logo" width="230">
<br>Frytea's MkDocs Material<br>Boilerplate - Starter Kit
</h1>

![Eyecatch image of MkDocs Material Boilerplate (Starter Kit)](https://raw.githubusercontent.com/peaceiris/mkdocs-material-boilerplate/master/docs_sample/images/material.png)



[![GitHub license](https://img.shields.io/github/license/songtianlun/frytea-docs)](https://github.com/songtianlun/frytea-docs/blob/master/LICENSE)
[![GitHub Actions status](https://github.com/songtianlun/frytea-docs/workflows/github%20pages/badge.svg)](https://github.com/songtianlun/frytea-docs/actions)
[![GitHub stars](https://img.shields.io/github/stars/songtianlun/frytea-docs)](https://github.com/songtianlun/frytea-docs/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/songtianlun/frytea-docs)](https://github.com/songtianlun/frytea-docs/network)

<!-- https://shields.io/ -->
<!-- https://microbadger.com/ -->



## Details

Read more 👉 [Documentation - MkDocs Material Boilerplate]

[Documentation - MkDocs Material Boilerplate]: https://peaceiris.github.io/mkdocs-material-boilerplate/



## Quick start

```sh
git clone https://github.com/peaceiris/mkdocs-material-boilerplate.git
cd mkdocs-material-boilerplate
pipenv sync --dev
pipenv shell
inv serve --config-file mkdocs-sample.yml
```

## GitHub Action

### (1) Add deploy Key

Generate deploy key ssh-keygen -t rsa -b 4096 -C "your@email.com" -f mkdocs -N ""
Go to "Settings > Deploy Keys" of repository.
Add your public key within "Allow write access" option.
Go to "Settings > Secrets" of repository.
Add your private deploy key as ACTIONS_DEPLOY_KEY

### (2) Workflow

```yml
workflow "MkDocs workflow" {
  on = "push"
  resolves = ["Build and deploy"]
}

action "branch-filter" {
  uses = "actions/bin/filter@master"
  args = "branch master"
}

action "Build and deploy" {
  needs = "branch-filter"
  uses = "peaceiris/actions-mkdocs-gh-pages@v1.2.0"
  env = {
    MKDOCS_BUILD_OPTIONS = "--config-file ./mkdocs-sample.yml"
  }
  secrets = ["ACTIONS_DEPLOY_KEY"]
}
```

### (3) Push to master branch

When you push to master branch, GitHub Actions runs.

## Links

- [mkdocs/mkdocs: Project documentation with Markdown - GitHub]
- [squidfunk/mkdocs-material: A Material Design theme for MkDocs]
- [peaceiris/mkdocs-material-boilerplate: Work in GitHub Action]
- [mkdocs-material-boilerplate: Old Work in GitHub Action]

[mkdocs/mkdocs: Project documentation with Markdown - GitHub]: https://github.com/mkdocs/mkdocs/
[squidfunk/mkdocs-material: A Material Design theme for MkDocs]: https://github.com/squidfunk/mkdocs-material
[peaceiris/actions-mkdocs-gh-pages: Work in GitHub Action]: https://github.com/peaceiris/actions-mkdocs-gh-pages
[peaceiris/mkdocs-material-boilerplate: Old Work in GitHub Action]: https://github.com/peaceiris/mkdocs-material-boilerplate



## License

- [MIT License]
- [The graduate cap icon] made by [Freepik] from [www.flaticon.com] is licensed by [CC 3.0 BY]

[MIT License]: https://github.com/peaceiris/mkdocs-material-boilerplate/blob/master/LICENSE
[The graduate cap icon]: https://www.flaticon.com/free-icon/graduate-cap_62627
[Freepik]: https://www.freepik.com/
[www.flaticon.com]: https://www.flaticon.com/
[CC 3.0 BY]: http://creativecommons.org/licenses/by/3.0/



## Support author

- [Amazon wish list](http://amzn.asia/ilWK0Yj)
