Naarad
======

Naarad aggregates all your KGP related news from facebook pages to one place. This repository is mainly push updates to github pages, [naarad-source](https://github.com/metakgp/naarad-source) is the main development repository.

Maintainers : [Athitya Kumar](https://github.com/athityakumar) and [Ayush Goyal](https://github.com/DefCon-007).


## How does it work?

Naarad gets the content from the specified pages using Facebook's graph API. We
use [facepy](https://github.com/hargup/facepy) as the python frontend for the
api. It is deployed at Travis CI where every build updates Naarad and  pushes a new 
commit, which triggers Travis again.  
Travis CI link: https://travis-ci.org/americast/naarad


## How to use Naarad

* Get a Facebook API token and save it in file name `ACCESS_TOKEN`. See this [StackOverflow Answer](http://stackoverflow.com/a/16054555/1780891).
* Naarad runs exclusively on Python 3, you can [conda](http://conda.pydata.org/miniconda.html) to easily switch between Python 2 and Python 3 environments.
* Install `facepy`. As of now you'll have to use `hargup`'s fork of `facepy` as
    the code in the original repository doesn't handle downloading of image
    files well. Pull Request is in process.
    * Clone https://github.com/hargup/facepy
    * Change into the directory and do `pip install -e .`
* Run `deploy.sh` to push the changes to `master`. The website is generated
    through the `docs/` directory. `deploy.sh` runs
    `fbscrapper.py` which creates json files containing feeds, and then runs
    `frontend.py` which converts the json feed into into nice html according to
    a template specified in `feed.tmpl`.


## License

AGPL
