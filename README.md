# Dot

Dot is an interactive dot plot viewer for genome-genome alignments.

Dot is publicly available here: [dot.sandbox.bio](https://dot.sandbox.bio)
And can also be used locally by cloning this repository and simply opening the index.html file in a web browser. 


## Generating the input data
After aligning genome assemblies or finished genomes against each other with MUMmer's nucmer, the alignments can be visualized with Dot. 
Instead of generating static dot plot images on the command-line, Dot lets you interact with the alignments by zooming in and investigating regions in detail. 

To prepare a `.delta` file (nucmer output) for Dot, run the `DotPrep.py` python (3.6) script included in this repo first.

The `DotPrep.py` script will apply a unique anchor filtering algorithm to mark alignments as unique or repetitive. This algorithm analyzes all of the alignments, and it needs to see unfiltered data to determine which alignments are repetitive, so make sure to run nucmer without any filtering options and without running delta-filter on the `.delta` file before passing it into `DotPrep.py`. 

The output of `DotPrep.py` includes the `*.coords` and `*.coords.idx` that should be used with Dot for visualization.
