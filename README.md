[![Build Status](https://travis-ci.org/prideout/snowy.svg?branch=master)](https://travis-ci.org/prideout/snowy)

## Snowy

This is a tiny Python 3 module for manipulating and generating images.
- Simple and flat API. See the [documentation](https://github.prideout.net/snowy/).
- Supports resize and blur with a variety of filters.
- Honors a specified wrap mode for proper boundary behavior.
- Supports simple OpenEXR images (never clamps colors).
- Written purely in Python 3 and accelerated using [numba](https://numba.pydata.org/).
- Efficiently generates gradient noise and distance fields.

Snowy is somewhat similar to [pillow](https://python-pillow.org/) and
[scikit-image](https://scikit-image.org/), but has a small feature set with some unique abilities.
Painting and 2D paths are outside the scope of the library. See
  [pycairo](https://pycairo.readthedocs.io/en/latest/) or
  [skia-pathops](https://github.com/fonttools/skia-pathops).

<!--

  API Change:
    deprecate load/save, but do not remove
    rename to import / export because they do a lot of manip
      such as 4-channel extension, delinearization, etc.
      Also: export should not take an imageio string. Instead it should have a bool
    for delinearization.

  Make a video with iterm2 and ipython (or bpython or ptpython)

  ---

  arbitrary rotation

  CPCF's

  height field AO

  variable radius blur (radius multiplier is a fn not a constant)
    test with a distance field + gradient

  prefiltering as seen in docs/hoppe

  ---

  reduce_colors
  io can have create_movie
      heat wave example
      brownian loop zoom example
  io can have generate_gallery for making HTML, and optional forced width/height/filter
  pixel art scaling algorithm(s)
  add fractal.py
      mandelbrot example from numba
      also this: https://en.wikipedia.org/wiki/Buddhabrot
  generate voronoi or triangulations, like the little test images here:
      http://agea.github.io/tutorial.md/


Making a release:

  1. Update the version # in generate.py and setup.py, then run generate.py
  2. git push
  3. python3 setup.py sdist bdist_wheel
  4. twine upload dist/*

  consider using travis for this:
      https://docs.travis-ci.com/user/deployment/pypi/

Testing a release:

  open https://pypi.org/project/snowy/
  cd ~
  python3 -m venv snowy_test
  source snowy_test/bin/activate
  pip install snowy
  python3
      import snowy; import numpy as np
      n = snowy.generate_noise(100, 100, frequency=4, seed=42, wrapx=True)
      snowy.show(n)
      deactivate
  see also:
      https://docs.python-guide.org/dev/virtualenvs/

-->
