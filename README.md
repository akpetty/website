
See `environment.yml` for the
complete dependency list.

You can create a conda environment with all required dependencies by running
`conda env create` in the root of the repository. To activate the environment
and run the build use `source activate urubu`.

## Compiling the site

Use the `Makefile`:

    make
    make serve

The command `make serve` will start a simple server at the `_build` folder
where the built HTML files are.
Point your browser to [http://127.0.0.1:8000](http://127.0.0.1:8000)
to view the site.
Use `Ctrl+C` to kill the server.

## The theme

The website theme is made using [bootstrap](http://getbootstrap.com/)
and tweaked from the Cosmo [Bootswatch](http://bootswatch.com/) theme.
Icons are provided by [FontAwesome](http://fontawesome.io/) and
[Academicons](http://jpswalsh.github.io/academicons/).

The Jinja2 templates and CSS are located in the `_layouts` and `css` folders.
I really should make this theme more generic and provide it to the world.
But, you know, time and things.
You can still use it by copying the folders to your own project.
I can't guarantee that things will work without my specific folder structure.

## Adding an article/talk/course/software

The papers, talks, courses and software entries are `.md` files in the
corresponding folders.
The site theme takes a lot of extra metadata in the post to make the "Info"
section of each entry.

To add a new entry, create the `.md` file in the corresponding folder.

## Metadata for entries

### Papers

Required:

    title: Geophysical tutorial: Euler deconvolution of potential-field data
    date: yyyy-mm-dd
    layout: publication

Note that `citation` has to be in a single line.

Optional:

    repository: pinga-lab/paper-tle-euler-tutorial
    doi: 10.1190/tle33040448.1
    supplement: 10.6084/m9.figshare.923450
    thumbnail: paper-tle-euler-tutorial-2014.png
    pdf: paper-tle.pdf
    author: uieda, oliveira-jr, barbosa
    journal: The Leading Edge
    citation: Uieda, L., V. C. Oliveira Jr, and V. C. F. Barbosa (2014), Geophysical tutorial: Euler deconvolution of potential-field data, The Leading Edge, 33(4), 448-450, doi:10.1190/tle33040448.1
    oa: true
    inreview: true
    accepted: true
    alm: true

* `authors` is a list of ids defined in the `_site.yml` file. Each id
  maps to an author name.
* An entry with `oa: true` will be marked as open-acess.
* `thumbnail`  should be the name of a 600 x 300 pixel figure in
  `/images/thumb`
* `pdf` should be the name of PDF file in the `pdf` folder
* `inreview: true` will mark the entry as under peer-review (unpublished).
* `accepted: true` will mark the entry as accepted for publication (after
  peer-review but not yet published).
* `alm: true` will embed Article Level Metrics for that entry.

### Talks

Required:

    title: Use of the "shape-of-anomaly" data misfit in 3D inversion by planting anomalous densities
    presentation: oral
    date: yyyy-mm-dd
    layout: publication

`presentation` can be either `oral` or `poster`.

Optional:

    event: SEG Annual Meeting
    pdf: seg-2012.pdf
    repository: leouieda/seg2012
    slides: 10.6084/m9.figshare.156864
    poster: 10.6084/m9.figshare.1089987
    doi: 10.1190/segam2012-0383.1
    thumbnail: seg2012.png
    citation: 


## Automatic deploy with TravisCI

The site is automatically built and deployed to
[leouieda/leouieda.github.com](https://github.com/leouieda/leouieda.github.com)
every time a commit is pushed to the *master* branch.
See files `.travis.yml` and `ci-tools/deply-gh-pages.sh`.

Inspired by
[Sleepy Coders](http://sleepycoders.blogspot.com.au/2013/03/sharing-travis-ci-generated-files.html)
and
[Mathieu Leplatre](http://blog.mathieu-leplatre.info/publish-your-pelican-blog-on-github-pages-via-travis-ci.html).

[![TravisCI status](http://img.shields.io/travis/leouieda/website.svg?style=flat)](https://travis-ci.org/leouieda/website)

## License

[![Creative Commons
License](https://i.creativecommons.org/l/by/4.0/88x31.png)](http://creativecommons.org/licenses/by/4.0/)
This work is licensed under a
[Creative Commons Attribution 4.0 International
License](http://creativecommons.org/licenses/by/4.0/).
