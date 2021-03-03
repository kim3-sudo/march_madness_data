R and RST Usage
***************

To use the :code:`.rds` file, go to the file that you'd like to use. GitHub is unable to render these files, but you can right-click on the raw file and copy the link for it. Then, use the :code:`readRDS()` function in R to read the dataset in. That might look something like this. Here, I'll read in the RDS for the 2010 play-by-play data into an object called :code:`pbp2010`.

.. role:: R(code)
  :language: R

:R:`pbp2010 <- readRDS(url('https://github.com/kim3-sudo/march_madness_data/blob/main/PlayByPlay_2010/Events_2010.rds?raw=true'))`
