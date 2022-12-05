# Personal-Inventory
App that catalogues all collectibles that I own.

## [Live Site](https://xmoose25x.github.io/Personal-Inventory/)

## Technology
* [Jekyll 4.2.2](https://jekyllrb.com/)
* [GitHub Actions Workflow](https://docs.github.com/en/actions/using-workflows)
    * [helaili's jekyll-action](https://github.com/helaili/jekyll-action) is used, though this should be updated to the [GitHub provided solution](https://github.com/github/pages-gem/issues/651).
* [GitHub Pages](https://pages.github.com/)

## Build & Run Locally
* `bundle exec jekyll serve`
    * Runs at [http://localhost:4000](http://localhost:4000)

## Deployment
* The [github-pages.yml](./.github/workflows/github-pages.yml) file controls automatic deployment [this page](https://xmoose25x.github.io/Personal-Inventory/).

## Image Assets
All images are manually added to this project's repository to ensure data longevity. As such, images are sourced from various sites when the original manufacturer's imagery is missing or out of date. The following table shows the expected size for each asset:

|  Collection  | Width | Height | File Type |
|--------------|-------|--------|-----------|
|    Amiibo    | 110px | 118px  |  .PNG     |
| Switch Games | 500px | 810px  |  .JPG     |
