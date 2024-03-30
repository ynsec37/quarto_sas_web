Run SAS in Quarto Website and publish to GitHub pages

- R and RStudio with Quarto
- Python and Java
- SAS OnDemand for Academics

## Steps

1. install python package
   
  ``` 
  pip install saspy
  pip install sas_kernel
  ```

1. configure [`sascfg_personal.py`](configure_saspy/sascfg_personal.py) and [`_authinfo`](configure_saspy/_authinfo)

  see details: https://support.sas.com/ondemand/saspy.html

1. create Quarto website project from RStudio while ticking create a git repository

1. update git configuration 
   
1. add new [`sas.qmd`](sas.qmd) file 

  ```qmd
  ---
  title: "Quarto Demo with SAS"
  format: html
  jupyter: sas
  self-contained: true
  ---
  ```

1. set `freeze` in _quarto.yml

  ```
  execute:
    freeze: auto
  ```

1. run `quarto render` in terminal to render the website locally and review the output

1. create repository in GitHub and set remote

  `git remote add origin `

1.  run `quarto publish gh-pages` in terminal and publish to `gh-pages`
   
1. create the [`.github/workflows/publish.yml`](.github/workflows/publish.yml) to use GitHub Actions 

## References

- [Running SAS in Quarto](https://www.harveyl888.com/post/2022-06-27-quarto_sas_01/)

- [Publish to GitHub Pages](https://quarto.org/docs/publishing/github-pages.html)
  
- https://www.harveyl888.com/outputs/quarto_02.html

- https://github.com/bvancil/quarto-sas-example

- https://github.com/baselr/configSAS
  
