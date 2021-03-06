Python and RST Usage
***************

To use the :code:`.rds` file in Python, go to the file that you'd like to use. GitHub is unable to render these files, but you can right-click on the raw file and copy the link for it. Then, use the :code:`read_r()` function from the pyreadr library to read the dataset in. That might look something like this. Here, I'll read in the RDS for the 2010 play-by-play data into an object called :code:`pbp2010`.

You may also need to get the pyreadr library, if you don't already have it in your Python installation. You can get it using:

::
  pip install pyreadr

.. code-block:: python
  :linenos:
  
  import pyreadr
  url = "https://github.com/kim3-sudo/march_madness_data/blob/main/PlayByPlay_2010/Events_2010.rds?raw=true"
  scratch = "./pbp2010.rda"
  local = pyreadr.download_file(url, scratch)
  result = pyreadr.read_r(local)
  df = result[None]

If you are reading the file straight off of the repository, you need to first download it into a temporary or scratch location using the :code:`download_file()` function from the pyreadr library. You can then load in the file directly from your scratch location. :code:`read_r()` does not support Internet URLs.

When you use the :code:`read_r()` function, it loads the contents of the RDS into a dictionary where keys are the names of objects and the values are Python objects. Since RDS files only have one object, use :code:`None` as the key.
