# Bears Classifier

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/zxul767/bears/main?urlpath=%2Fvoila%2Frender%2Fbears_classifier.ipynb)

A toy classifier that distinguishes between black, grizzly and teddy bears, from the [`fastai`](https://course.fast.ai/) course (chapter 2).

# FAQ
**How did you generate the `requirements.txt` file?**

I use [`poetry`](https://python-poetry.org) as my dependency manager, so I had to do the following:

```sh
poetry export --without-hashes -f requirements.txt --output requirements.txt
```

The resulting `requirements.txt` file is large because it contains *all transitive dependencies* in absolute versions. If you don't care about complete reproducibility, you can also create a simpler file (see [this repo](https://github.com/mihailthebuilder/bearly)) which contains just the top level dependencies (the same ones you'll find in `pyproject.toml` used by `poetry`). 

**Why do you have a `runtime.txt` file?**

To instruct Binder to use Python 3.8. Without it, Binder would complain about not finding `numpy==1.22.4`. This happens because `poetry` resolved dependencies in my local machine using Python 3.8.5 (as specified in the `pyproject.toml` file).
